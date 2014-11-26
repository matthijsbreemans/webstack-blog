title: Het Nancy webframework hosten op Heroku dankzij Owin
tags:
  - .NET
  - Github
  - Heroku
  - Katana
  - Mono
  - Nancy
  - Owin
id: 193
categories:
- Coding
date: 2014-04-29 21:45:29
---

Eerder [berichte ik al over Heroku's PaaS dienst](https://webstack.nl/2014/03/gratis-paas-diensten/ "Gratis PaaS diensten") en [vertelde](https://webstack.nl/2014/04/self-hosted-signalr-met-owin/ "Self-hosted SignalR met Owin") ik ook al wat over Owin en Katana. Onlangs kwam ik erachter dat Heroku het Mono project ondersteunde. [Mono](http://mono-project.org) is een opensource implementatie van Microsoft's .NET en zorgt er onder andere voor dat je .NET applicaties onder Linux kan draaien. Doormiddel een [speciaal buildpack](http://friism.com/running-net-on-heroku) kan Heroku voor jou je .NET applicatie rechtstreeks vanuit een Git repository compilen

Dankzij Owin is het nu mogelijk om self hosted applicaties te draaien die niet meer onder IIS moeten draaien en hierdoor volledig in Mono kunnen draaien zonder IIS. Microsoft heeft met haar eigen Owin implementatie genaamd Katana support voor WebApi en SignalR geleverd en deze kunnen dus zonder problemen binnen Owin draaien. Beide frameworks hebben zo snel van IIS/ASP.NET af kunnen stappen omdat hier vanaf het begin rekening mee is gehouden. Dat geldt helaas niet voor ASP.NET MVC, deze is te diep verbonden met ASP.NET welke weer zwaar op IIS ondersteuning leunt dat het maar de vraag is of ASP.NET MVC ooit in Owin zal draaien.

Gelukkig is er een ander web framework voor .NET genaamd [Nancy](http://nancyfx.org). Nancy is vergelijkbaar met het Ruby framework [Sinatra ](http://sinatrarb.com)en is gemaakt voor websites en webservices zonder dat het in de weg zit met zogenaamde "[plumbing](http://www.johndcook.com/blog/2011/11/15/plumber-programmers/)". Ondersteund Nancy ook MVC vraag je jezelf dan af? Jazeker maar het is niet verplicht om het MVC pattern te gebruiken. Uiteindelijk is Nancy maar een simpel endpoint dat naar Http Requests luistert. Gelukkig kan je ook gewoon MVC gebruiken zoals je dat wilt. Je kan Views laten serveren vanuit een Views map, Models aanmaken en je requests er naar toe mappen net zoals bij de reguliere ASP.NET MVC

Ik heb zelf een klein voorbeeld gemaakt welke een simpele Nancy applicatie door middel van Owin op [Heroku](http://heroku.net) gehost is. De source is [hier op Github](https://github.com/matthijsbreemans/nancy-owin-heroku) te vinden.

Hoe moet je het draaien?
```
git clone https://github.com/matthijsbreemans/nancy-owin-heroku.git
cd nancy-owin-heroku
heroku create
heroku config:add BUILDPACK_URL=https://github.com/friism/heroku-buildpack-mono/
git push heroku master
```

Niet vergeten een worker aan je Heroku app te koppelen en als het goed is kan je nu naar de app navigeren met je browser.