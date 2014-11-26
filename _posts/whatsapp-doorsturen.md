title: "WhatsApp-Forward, eenvoudig WhatsApp berichten doorsturen"
tags:
  - "C#"
  - Github
  - WhatsApp
  - WhatsApp doorsturen
id: 233
categories:
  - Coding
  - WhatsApp
date: 2014-05-10 12:39:45
---

Al eerder was ik bezig geweest met de [WhatsApp API voor C#](https://github.com/perezdidac/WhatsAPINet). Na een paar proof of concept's met SignalR en OWIN heb ik toch maar even iets bruikbaars in elkaar geknutseld. Het eindproduct is [WhatsApp-Forward](https://github.com/matthijsbreemans/whatsapp-forward) geworden! Het is een eenvoudige console applicatie welke naar berichten van een [WhatsApp](http://whatsapp.com) account luisterd en deze doorstuurd naar een vooraf gedefinieerd telefoon nummer. Die gene die het doorgestuurde bericht ontvangt kan hier ook weer eenvoudig op reageren, dit kan een persoon zijn maar ook WhatsApp groepen. Ook kan er eenvoudig opgevraagd worden in welke groepen de gebruiker zit.

<!-- more -->
Wat wordt er nu ondersteund

*   WhatsApp doorsturen naar een andere telefoon
*   Reageren op berichten
*   Groepen opvragen
*   Reageren in die groepen
Wat komt er in de toekomst in

*   Betere groepen ondersteuning
*   Media berichten doorsturen
*   Online/offline status bewerken
Let wel op de volgende dingen

*   Je WhatsApp account werkt nog maar via deze applicatie, indien je weer gebruik wil maken van de officiele WhatsApp app dan moet het telefoon nummer weer geactiveerd worden en dan zal deze applicatie niet meer werken
*   De applicatie stuurt alleen berichten door als deze actief is
*   De applicatie werkt niet met proxy servers
*   Er zit geen garantie op en ik ben ook niet verantwoordelijk voor enige schade aan het WhatsApp account
De source code van de alpha versie is [hier op Github](https://github.com/matthijsbreemans/whatsapp-forward) te vinden

Telefoon nummer, wachtwoord, naam en doorstuur nummer dient te worden ingesteld in de config file

Voorbeeld:
```
<add key="phonenumber" value="31612345678" />
<add key="password" value="password" />
<add key="displayname" value="whatsapp" />
<add key="forward" value="31600000000@s.whatsapp.net" />
```
Je gebruikers naam is je telefoon nummer zonder + of 0 maar met landcode. Het wachtwoord kan worden achterhaald door een nieuw account aan te maken via [https://github.com/perezdidac/WhatsAPINet](https://github.com/perezdidac/WhatsAPINet) 's WhatsAppPort

Je kan berichten terugsturen vanaf het telefoon nummer dat het doorgestuurde bericht heeft ontvangen bij door een bericht terug te sturen met !#(whatsapp account naam (31512345678@s.whatsapp.net) bericht

Voorbeeld: !#31612345678@s.whatsapp.net test