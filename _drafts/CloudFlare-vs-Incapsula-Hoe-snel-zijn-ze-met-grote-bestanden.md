title: "CloudFlare vs Incapsula: Hoe snel zijn ze met grote bestanden?"
tags:
  - CDN
  - CloudFlare
  - Content Delivery Network
  - Incapsula
id: 149
categories:
  - CloudFlare
  - Content Delivery Networks
  - Incapsula
---

Al [meerdere](http://webstack.nl/2014/03/gratis-content-delivery-networks-welk-cdn-is-de-beste/) [keren](http://webstack.nl/2014/04/cloudflare-vs-incapsula-site-optimalisatie/) zijn hier gelijkenissen en de verschillen tussen [CloudFlare](http://cloudflare.com) en [Incapsula](http://incapsula.com) vergeleken en uitgelegd. Deze keer wordt er gekeken hoe beide CDN's omgaan met grote bestanden. Beide CDN's passen een vorm van caching toe, meestal beperkt zich deze tot de webpagina en die kan ook on-the-fly gecomprimeerd worden. Met grote bestanden gaat dit wat lastiger en kan er eigenlijk geen on-the-fly optimalisaties worden toegepast.

Onze test omgeving bestaat uit een server met en Xeon processor, 16GB RAM en een 1Gbit dedicated verbinding in Parijs, Frankrijk op het netwerk van [Free.fr](https://www.robtex.com/as/as12876.html). Beide CDN's hebben ook een PoP in Parijs wat er voor zou zorgen dat de snelste route gekozen wordt. Om de hardeschijf als bottleneck uit te sluiten wordt wget met argumenten -O /dev/null gebruikt. Verder wordt het gemiddelde van 10 download's van een bestand van 100MB genomen.

**Zonder CDN: **900MB/s (localhost)

**CloudFlare: **5.01MB/s (20seconden)

**Incapsula: **4.55MB/s (22seconden)

**Externe server: **82MB/s

Er kan hier uit concluderen dat het verschil tussen beide erg klein is. CloudFlare is wat sneller maar het verschil is redelijk verwaarloosbaar. Wat wel opvalt is het grote snelheidsverschil tussen het gebruik van een CDN en zonder CDN. Kennelijk zijn diensten zoals Incapsula minder geschikt voor deze toepassingen en kan er beter gebruik worden gemaakt van een aparte CDN dienst voor het server van bestanden, zoals bijvoorbeeld [Rackspace Cloud Files](http://www.rackspace.com/cloud/files/) welke weer gebruik maakt van het immense netwerk van Akamai