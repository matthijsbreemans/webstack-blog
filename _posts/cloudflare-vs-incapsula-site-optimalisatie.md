title: "CloudFlare vs Incapsula: Site optimalisatie"
tags:
  - CDN
  - CloudFlare
  - Content Delivery Network
  - Incapsula
  - Page Speed
  - YSlow
id: 117
categories:
  - Content Delivery Networks
date: 2014-04-08 09:56:02
---

Eerder [schreef](https://webstack.nl/2014/03/gratis-content-delivery-networks-welk-cdn-is-de-beste/) ik al over de verschillen tussen [CloudFlare](http://cloudflare.com) en [Incapsula](http://incapsula.com).Beide diensten bieden onder andere aan om je website te versnellen, onder nadere door middel van goede bereikbaarheid, minification en gzip. Een goede manier om dit te meten is Yahoo's [YSlow](http://yslow.org) en Google's [Page Speed](https://developers.google.com/speed/pagespeed/). Deze berekenen een score en adviseren hoe je pagina geoptimaliseerd kan worden.

Om dit eenvoudig te testen heb ik gebruik gemaakt van [GTMetrix](http://gtmetrix.com), deze combineert beide technieken om de snelheid van de pagina te meten. Totaal zijn er 3 verschillende testen uitgevoerd, een met CloudFlare, een met Incapsula en een zonder beide. Alle drie de testen werden uitgevoerd op de zelfde Wordpress site op de zelfde host

<!-- more -->

#### Zonder

[![](https://i.imgur.com/IHLMYm5.png "Hosted by imgur.com")](http://imgur.com/IHLMYm5)

&nbsp;

Zonder enige CDN optimalisatie krijgt Wordpress en 96% Page Speed en een 86% YSlow rating.

#### CloudFlare

[![](https://i.imgur.com/wysVLHo.png "Hosted by imgur.com")](http://imgur.com/wysVLHo)

&nbsp;

CloudFlare zorgt voor een 97% score bij zowel Page Speed als YSlow,

&nbsp;

#### Incapsula

[![](https://i.imgur.com/P7GIVVK.png "Hosted by imgur.com")](http://imgur.com/P7GIVVK)

&nbsp;

Met Incapsula voor onze Wordpress site krijgt deze een 96% Page Speed cijfer en een 85% YSlow wat 1% minder is dan zonder CDN

#### Conclusie

CloudFlare voert daadwerkelijk verbeteringen door wat betreft de laadbaarheid van de pagina. De laadtijd rond de 1 seconde en meer dan de helft verkleining van de pagina grote zorgt er voor dat CloudFlare de Wordpress site op een 97% Page Speed en 97% YSlow score krijgt. Wat betreft Incapsula, deze zorgt amper voor verbetering in de pagina grote en krijgt zelfs een lager YSlow cijfer! Het advies; gebruik CloudFlare als je wilt dat je site ook daadwerkelijk sneller wordt!