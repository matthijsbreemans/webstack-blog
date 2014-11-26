title: Self-hosted SignalR met Owin
tags:
  - .NET
  - "C#"
  - Katana
  - Microsoft
  - Owin
  - SignalR
  - WhatsApp
id: 185
categories:
  - Coding
date: 2014-04-23 22:51:52
---

Onlangs ben ik bezig geweest met het uitwerken van een nuttige toepassing van de C# Api voor WhatsApp (GitHub fork [hier](https://github.com/matthijsbreemans/WhatsAPINet)). Iedereen weet ondertussen dat de openheid en compatibiliteit het grote gemis is bij WhatsApp dus het leek me leuk om wat te gaan spelen met een zelf geschreven crossplatform client. Mijn keuze is uiteindelijk op een implementatie van [WhatsApi](https://github.com/venomous0x/WhatsAPI) geworden. Ook zocht ik al een tijdje naar een nuttige toepassing om [SignalR](http://en.wikipedia.org/wiki/SignalR) te gaan gebruiken (op een simpele oldschool Ilse chat room na) en is mijn keuze uiteindelijk gevallen op een self hosted implementatie van Owin in combinatie met SignalR.

Nieuwsgierig wat SignalR en/of Owin nou precies inhoud?

<!-- more -->

Bekijk dan deze goede talk over [Owin](http://owin.org/), [Katana](https://katanaproject.codeplex.com/documentation) en [Helios](http://www.infoq.com/news/2014/02/helios):
<iframe src="//www.youtube-nocookie.com/embed/G5Kf7R07l_g" height="480" width="853" allowfullscreen="" frameborder="0"></iframe>

Ook geinteresseerd in SignalR?

<iframe src="//www.youtube-nocookie.com/embed/4sBVcu-NBP4" height="480" width="640" allowfullscreen="" frameborder="0"></iframe>

Ben je benieuwd hoe je snel Owin en Signalr kan combineren? Op de [asp.net site staat](http://www.asp.net/signalr/overview/signalr-20/getting-started-with-signalr-20/tutorial-signalr-20-self-host) een tutorial over hoe simpel het is om deze twee te combineren en hier mee zeer simpel een realtime applicatie neer te kunnen zetten zonder IIS.