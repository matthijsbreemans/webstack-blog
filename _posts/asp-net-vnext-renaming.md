title: "ASP.NET vNext, renamen en de introductie van DNX!"
tags:
  - .NET
  - ASP.NET
  - "C#"
  - Microsoft
categories:
  - ASP.NET vNext
  - Coding
  - Microsoft
date: 2015-03-20 17:31:13
---

Het speelde al een tijdje bij de ontwikkeling van ASP.NET vNext maar tijdens [een van de laatste Community Stand Up's](https://www.youtube.com/watch?v=-qt0POsiAF8&list=PL0M0zPgJ3HSftTAAHttA3JQU4vOjXFquF&index=1) is er besloten dat de bekende vNext commando's zoals k en kpm hernoemd worden om eenduidigere en unieke commando's te gebruiken

### dnvm

dnvm is de vervanger van KVM. Als je net ASP.NET vNext hebt geinstalleerd begin je met dnvm. dnvm zorgt ervoor dat er een runtime versie geinstalleerd wordt en hiermee kan je ook de verschillende runtimes (mocht je die hebben) managen. Ook is het mogelijk om naar een andere versie switchen. Zie [https://github.com/aspnet/Home/wiki/version-manager](https://github.com/aspnet/Home/wiki/version-manager) voor meer info.

### dnx (dot Net X?)

DNX is de vervanger van K. Als je een vNext applicatie wilt draaien gebruik je dnx run. Voor meer informatie zie [https://github.com/aspnet/Home#optimistic-dnx](https://github.com/aspnet/Home#optimistic-dnx). Eventueel kan er in het project.json bestand nog andere startup commando's worden opgegeven. Ook vervangt dnx het oude KRE commando omdat de CLR en CLR bootstrappers nu als een NuGet packages aangeboden worden.

<!-- more -->

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/-qt0POsiAF8?list=PL0M0zPgJ3HSftTAAHttA3JQU4vOjXFquF" frameborder="0" allowfullscreen></iframe>