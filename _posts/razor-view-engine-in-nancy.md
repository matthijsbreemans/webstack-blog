title: Razor View Engine in Nancy
tags:
  - .NET
  - "C#"
  - Github
  - Heroku
  - Katana
  - Mono
  - Nancy
  - Owin
id: 209
categories:
  - Coding
date: 2014-05-06 20:51:45
---

Het vervolg op mijn [vorige post](https://webstack.nl/2014/04/het-nancy-webframework-hosten-op-heroku-dankzij-owin/ "Het Nancy webframework hosten op Heroku dankzij Owin") waarin ik blogde over Nancy in combinatie met Owin en Heroku. Toen was het nog een simpele applicatie, maar de kracht van Nancy is dat het zo flexibel is dat je ook gewoon [Razor cshtml view's](https://github.com/NancyFx/Nancy/wiki/Razor-View-Engine) kan laten renderen. Hierdoor kan je ook gewoon traditionele MVC applicaties met Nancy maken. Het grote verschil met ASP.NET MVC is dat Nancy modules in plaats van controllers heeft. Ook moet eer een Nancy object wrapper in je View Model gebruikt worden.

<!-- more -->
Nu de installatie, eigenlijk is het heel erg simpel, een enkel [Nuget](http://nuget.org) commando is genoeg om Nancy de Razor Views te laten renderen.

*   Open de Nuget package manager console in Visual Studio
*   Voor het commando _Install-Package Nancy.ViewEngines.Razor_ uit

Als je ook wilt dat de solution zowel binnen Visual Studio als in Heroku (of Mono xbuild) gecompileerd kan worden dient er wel een kleine wijziging in het csproject bestand gemaakt te worden. Nancy Razor voegt namelijk een post-build actie toe om het debuggen mogelijk te maken. Vervang het toegevoegd post-build statement met [deze code](https://github.com/NancyFx/Nancy/issues/1082#issuecomment-20228265) . Let wel op de build nummers deze dienen te worden vervangen met de versie die door Nuget is geinstalleerd.

Ik heb op [Github een voorbeeld](https://github.com/matthijsbreemans/nancy-owin-heroku) solution staan welke zowel binnen Visual Studio 2013 als via Heroku gecompileerd kan worden.