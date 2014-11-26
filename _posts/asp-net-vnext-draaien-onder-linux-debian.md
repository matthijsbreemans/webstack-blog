title: ASP.NET vNext draaien onder Linux / Debian
tags:
  - .NET
  - ASP.NET
  - "C#"
  - debian
  - Linux
  - vNext
id: 277
categories:
  - ASP.NET vNext
  - Coding
  - Microsoft
date: 2014-08-26 10:57:54
---

[Eerder](https://webstack.nl/2014/08/asp-net-vnext-wat-is-het-en-wat-doet-het/) heb ik al een uitleg gegeven over wat ASP.NET vNext precies is. Nu beloofd Microsoft goede cross platform compatibiliteit, met Windows, Linux en OS X en was ik benieuwd hoe goed dit nu eigenlijk werkt op Linux. Ik heb hiervoor een Debian Wheezy installatie gebruikt welke ik heb geupgrade naar Debian Sid, of tewel Debian testing.

<!-- more -->
Commando's die beginnen met een # dienen uitgevoerd te worden als root of met sudo en commando's die beginnen met $ dienen als een normale users uitgevoerd te worden

Upgrade /etc/apt/sources.list naar Sid door alles te vervangen met het volgende:

```
deb http://ftp.nl.debian.org/debian unstable main contrib non-free
deb-src http://ftp.nl.debian.org/debian unstable main contrib non-free
```

Voer daarna de upgrade uit met:

```
#apt-get update &amp;&amp; apt-get dist-upgrade
```

Installeer wat benodigd heden die we later nodig hebben:
```
#apt-get install sudo unzip curl autoconf libtool gettext build-essential git
```
Installeer Mono 3.6.0 vanuit de repository van Xamarin

```
#wget http://download.mono-project.com/repo/xamarin.gpg
#apt-key add xamarin.gpg
#echo "deb http://download.mono-project.com/repo/debian wheezy main" &gt; /etc/apt/sources.list.d/mono-xamarin.list

#apt-get install mono-complete
```
Om ASP.NET vNext te draaien heb je minstens Mono 3.6.1 nodig, echte zit deze nu nog niet in de repository dus moeten we Mono van source compilen. Als je Mono wilt compilen heb je Mono zelf nodig dus daarom hebben we die net eerst geinstalleerd.

```
#git clone git://github.com/mono/mono.git
#cd mono
#./autogen.sh --prefix=/usr/local
#make
#make install
```

Als het goed is dan is nu de laatste versie van Mono geinstallerd, dit kan je controleren door mono -V in te typen

Standaard worden er geen certificaten ondersteund in Mono, deze dienen we dus te gaan installeren:
```
#certmgr -ssl -m https://go.microsoft.com<
#certmgr -ssl -m https://nugetgallery.blob.core.windows.net
#certmgr -ssl -m https://nuget.org
#certmgr -ssl -m https://www.myget.org
$mozroots --import --sync
```

Nu gaan we ASP.NET vNext installeren, omdat ASP.NET vNext nog in Alpha/Beta fase is willen we graag de laatste versie (alpha4 op dit moment)

```
$sudo curl https://raw.githubusercontent.com/aspnet/Home/dev/kvminstall.sh | sh &amp;&amp; source ~/.kre/kvm/kvm.sh
```

Als je toch liever een meer stabiele versie wilt kan je de master branch (alpha3 op dit moment) installeren met het volgende commando

```
$sudo curl https://raw.githubusercontent.com/aspnet/Home/master/kvminstall.sh | sh &amp;&amp; source~/.kre/kvm/kvm.sh
```

ASP.NET vNext is nu geinstalleerd en we gaan met de K Package Manager (kpm) de laatste packages ophalen.

```
$kvm upgrade
```
In principe kan je nu gewoon een ASP.NET project aanmaken zoals bijvoorbeeld hier beschreven staat.

Maar we gaan nog een stapje verder, er is namelijk een tool genaamd Yeoman welke het mogelijk maakt om eenvoudig project templates aan te maken. Voor Yeoman is wel Node.js nodig dus deze gaan we ook installeren
```
#curl -sL https://deb.nodesource.com/setup | bash -
#apt-get install nodejs
#npm install -g yo
```

Yeoman is nu geinstalleerd en we installeren het template voor vNext

```
#npm install -g generator-aspnet
```

Yeoman is nu geinstalleerd met de vNext project templates.

Omdat httpapi.dll en Kestrel nog geen native builds voor Linux hebben kunnen we van deze templates alleen de Consoleapplication draaien.

Start nu Yeoman op met yo en kies de Console Application template

[![](https://i.imgur.com/39vJi3o.png "Hosted by imgur.com")](http://imgur.com/39vJi3o)
Het kan zijn dat er wat error's komen bij een kpm restore omdat kpm de NuGet.config nog niet helemaal goed kan lezen onder Linux, dit kan je oplossen door het volgende commando te draaien
```
$kpm restore -s https://www.myget.org/F/aspnetmaster/ -f https://nuget.org/api/v2/
```
Ga nu naar de ConsoleApplication map die zojuist is aangemaakt en type
```
$k run
```
ASP.NET vNext zal nu het project.json project bestand lezen en alle dependencies inladen en doormiddel van de RyuJIT Program.cs draaien

Als je nu bijvoorbeeld de volgende regel aan je Program.cs toevoegt zal je zien dat het ook echt onder Linux draait
```
Console.WriteLine(string.Format("Currently running {0}", Environment.OSVersion));
```
[![](https://i.imgur.com/wMy4EUA.png "Hosted by imgur.com")](http://imgur.com/wMy4EUA)
Conclusie van ASP.NET vNext, het heeft erg veel potentie maar het is nog wel in alpha fase, verwacht dus dat er een hoop dingen nog niet werken.

Just-In-Time compiling van .NET onder Linux, wie had dat ooit geacht, ik niet in ieder geval!
