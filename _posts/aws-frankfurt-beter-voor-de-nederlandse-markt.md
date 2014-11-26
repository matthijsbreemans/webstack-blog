title: "AWS Frankfurt, beter voor de Nederlandse markt?"
date: 2014-10-25 10:05:29
tags:
  - Amazon Web Services
  - AWS
  - Cloud
categories:
  - AWS
  - Cloud
---
Afgelopen maandag [kondigde](https://aws.amazon.com/blogs/aws/aws-region-germany/) Amazon aan dat ze per direct Frankfurt als locatie hebben toegevoegd aan hun AWS infrastructuur. Tot voorheen was Ierland de enige PoP van AWS voor Europa en ook voor Afrika was Ierland het dichtst bijzijnde. Goed nieuws voor ons Europeanen dus die nu de keuzen hebben uit twee PoPś. Helemaal voor Nederland zou je denken omdat wij hemelsbreed maar 360km van Frankfurt verwijderd zijn in plaats van de 760km van Dublin (vanaf Amsterdam). Klinkt alsof we allemaal van Dublin naar Frankfurt moeten overstappen dus. Meten is weten en daarom een kleine benchmark welke AWS locatie nu het snelste is voor Nederland.

<!-- more -->

Ik heb voor de test een t2.medium instance in zowel Ierland als Frankfurt opgezet en als test locaties mijn 90/9mbit Ziggo verbinding en een [DigitalOcean](https://www.digitalocean.com/?refcode=1fbe2ead8d3e) droplet gebruikt. Om de maximale snelheid van mijn DigitalOcean droplet te testen heb ik de LeaseWebś filemirror gebruikt. Overigens heeft zowel Ziggo als DigitalOcean peering met Amazon op de AMSIX. De verbindingen van Ierland en Frankfurt maken beiden gebruik van deze peering.

Ping tijden:
``` 
|         	| Ierland  	| Frankfurt 	|
|---------	|----------	|-----------	|
| Ziggo   	| 31.672ms 	| 33.036ms  	|
| DO AMS3 	| 21.626ms 	| 18.206ms  	|
```

Speedtest:
```
|         | Ierland   | Frankfurt | LeaseWeb mirror |
|---------|-----------|-----------|-----------------|
| Ziggo   | 9.9MB/s   | 9.8MB/s   | 10.1MB/s        |
| DO AMS3 | 49.28MB/s | 43.23MB/s | 103.1MB/s       |
````
Traceroute (hops):
```
|         | Ierland | Frankfurt |
|---------|---------|-----------|
| Ziggo   | 10 hops | 11 hops   |
| DO AMS3 | 10 hops | 11 hops   |
```

Uit deze snelle benchmark kan je concluderen dat de nieuwe locatie van AWS in Frnankfurt de verwachtingen niet kan waar maken. Waar je zou verwachten dat deze juist sneller is voor Nederland ziet het er uit dat Frankfurt toch langzamer is dan Ierland. Frankfurt zal dus meer een voordeel opleveren voor Oost Europa dan voor Nederland.