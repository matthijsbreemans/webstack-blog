title: Gratis PaaS diensten
tags:
  - Amazon
  - AppHarbor
  - AWS
  - Azure
  - Google App Engine
  - Heroku
  - Microsoft
  - OpenShift
  - PaaS
  - Pagoda Box
  - Platform-As-A-Service
id: 41
categories:
  - Cloud
  - Platform-As-A-Service
date: 2014-03-23 12:57:29
---

Gratis PaaS? Ja gratis PaaS! Als je nog niet weet wat PaaS betekent is deze blog misschien niet voor je bedoeld. Als je toch graag iets met Platform-As-A-Service wilt gaan doen kan ik je adviseren om [dit ](http://www.dummies.com/how-to/content/what-is-platform-as-a-service-paas-in-cloud-comput.html)even te lezen.

In de wereld van de Cloud zijn eigenlijk maar drie grote spelers, namelijk [Amazon](http://aws.amazon.com/), [Microsoft](http://azure.com/) en [Google](http://cloud.google.com/). Amazon is er in gerold met hun Amazon Web Services (AWS) om overtollige servers te gaan verhuren. Dit bleek een ongekend succes te zijn, mede dankzij hun goede prijsmodel, en Amazon heeft hier nu groot op ingezet. Microsoft daarentegen is met hun Azure cloud meteen groots begonnen, waar het bij Amazon nog als een redelijk klein project begon hebben ze bij Microsoft hier gelijk groot op ingezet. Microsoft probeert met name de infrastructuur van grote bedrijven in de Azure cloud te krijgen en combineert dit met uitstekende integratie in het .NET framework en Windows. Google is daarentegen een andere weg bewandeld, ze zijn al erg lang bezig met de Google App Engine (GAE) en die was ook al vanaf het begin gratis maar de Google Compute Engine (GCE) is pas later beschikbaar gekomen.

<!--more-->

Maar goed, zoals de titel al zegt gaan we het hebben over gratis PaaS. Natuurlijk je kan bij AWS een jaar lang gratis gebruik maken van hun Free Tier model, Azure biedt een trial periode aan voor een paar maanden en bij Google kan je gratis gebruik maken van GAE maar niet van GCE. Zodra deze proefperiodes zijn verstreken gaat de rekening lopen en dan kan het een duur grapje worden.

We gaan het vandaag hebben over echt gratis PaaS diensten, een dienst waar jij als developer even snel een site de lucht in kan hijsen om die PoC te laten zien. Diensten die je in de beta fase gratis kunt gebruiken en daarna snel kan opschalen om het grote gebruik aan te kunnen.

Ik zelf als .NET developer maak altijd graag gebruik van de diensten van AppHarbor en als ik eens de Java kant op ging dan maakte ik gebruik van de GAE. Maar wat is er nu nog meer vroeg ik me eigenlijk af?

Sowieso als .NET developer mag je al snel de creditcard gaan trekken want op AppHarbor na ben ik nog geen andere .NET PaaS tegengekomen dat ook een volledig gratis plan aanbiedt.

Dus ben ik vandaag een zoektocht begonnen naar gratis PaaS omgevingen waar je als developer snel naar kan deployen.

Overigens heb ik alleen praktijk ervaring met AppHarbor, GAE en Pagoda Box. De overige PaaS diensten heb ik aan de hand van de documentatie bekeken en hier mijn conclusies uitgetrokken.

## [AppHarbor](http://www.appharbor.com/)

Zelf gebruik ik AppHarbor al een tijdje naar tevredenheid. Je kan via Git je ASP.NET applicatie naar de servers van AppHarbor sturen. Deze wordt dan bij AppHarbor gebuild en gedeployed op door jouw gekozen lokatie, dit kan EU of US zijn.

Cloud: AWS

**Voordelen**
- .NET!
- Veel addons
- Gratis bandbreedte
- Git repository
- Piggyback SSL

**Nadelen**
- Opschalen wordt meteen prijzig (begint bij 50euro)
- Geen eigen domein mogelijk
- Web worker opstarten duur 20+ seconden

## [Google App Engine](http://appengine.google.com/)

Google is al sinds 2008 bezig met de Google App Engine. In tegenstelling tot andere diensten werkt Google met een 24uur quota voor gratis diensten. Zodra je wilt dat je applicaitie blijft werken nadat deze is overschreven moet je je creditcard toevoegen. Dat Google al sinds 2008 bezig is met GAE is niet echt te merken aan de features die erop zitten, van Google mag je wel verwachten dat ze het maximale uit GAE halen maar dat gebeurd niet. GAE is leuk maar als je meer wilt kom je al snel uit bij de concurentie.

Cloud: Google

**Voordelen**
- Java/Python/Go/PHP
- Google infrastructuur
- Eigen domein mogelijk via Google Apps
- 24uur quota

**Nadelen**
- Geen gratis SQL
- Weinig talen, PHP en Go zijn nog experimental
- Geen gratis SSL (5euro per certificaat)
- Niet mogelijk om zelf een regio te kiezen

## [Heroku](http://www.heroku.com/)

Heroku is een van de eerste PaaS platformen, ze bestaan al sinds 2007 en in tegenstelling tot GAE is het wel echt een volwassen platform. Ze begonnen met Ruby maar bieden nu een meervoud van talen aan.

Cloud: AWS

**Voordelen**
- Java/Node/Ruby/Python
- Gratis PostgreSQL
- Gratis bandbreedte (tot 2TB/maand)
- Eigen domein mogelijk
- .NET mogelijk via Mono!

**Nadelen**
- SSL kost 20 euro per maand

## [Pagoda Box](https://pagodabox.com/)

Over Pagoda Box kan ik kort en krachtig zijn. Zoek je een PHP PaaS? Ga dan voor PB! Ze bieden alleen PHP aan maar blinken daar wel in uit. Onder andere deze blog draait op Pagoda Box.

Cloud: SoftLayer

**Voordelen**
- PHP
- Gratis eigendomein
- Gratis SSL
- Gratis background worker
- Gratis bandbreedte
- Git repositrory
- Mooie interface

**Nadelen**
- Alleen PHP
- Database alleen via een tunnel

## [Redhat OpenShift Online](http://openshift.com/)

Redhat OpenShift Online is gebaseerd op Redhat's openshift technologie. Openshift zorgt er voor dat erg veel talen ondersteund worden en dat is ook te zien. Ze bieden 16 verschillende 'gears' aan, van PHP tot aan SQL, welke je dan aan je applicatie kan koppelen.

Cloud: AWS

**Voordelen**
- Veel keuze door het OpenShift platform
- Gratis domein
- Gratis SSL
- Gratis bandbreedte
- Bij het koppelen van je creditcard nog meer gratis features

**Nadelen**
- Maximaal 3 gears