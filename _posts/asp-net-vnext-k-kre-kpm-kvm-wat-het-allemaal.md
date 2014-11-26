title: "ASP.NET vNext, K KRE KPM KVM, wat is het allemaal?"
tags:
  - .NET
  - ASP.NET
  - "C#"
  - Microsoft
  - vNext
id: 313
categories:
  - ASP.NET vNext
  - Coding
  - Microsoft
date: 2014-08-28 07:14:13
---

Nu [ASP.NET vNext steeds meer vorm](https://webstack.nl/2014/08/asp-net-vnext-wat-is-het-en-wat-doet-het/ "ASP.NET vNext, wat is het precies?") begint te krijgen, zelfs [onder Linux](https://webstack.nl/2014/08/asp-net-vnext-wat-is-het-en-wat-doet-het/ "ASP.NET vNext, wat is het en wat doet het?"), is er soms wat onduidelijkheid over alle K* applicaties, zie hier een uitleg over welke commando precies wat doet.

### KVM (K Version Manager)

Als je net ASP.NET vNext hebt geinstalleerd begin je met kvm. Kvm zorgt ervoor dat er een runtime versie geinstalleerd wordt en hiermee kan je ook de verschillende runtimes (mocht je die hebben) managen. Ook is het mogelijk om naar een andere versie switchen. Zie [https://github.com/aspnet/Home/wiki/version-manager](https://github.com/aspnet/Home/wiki/version-manager) voor meer info.

### KRE (K Runtime Engine)

KRE is de bootstrapper voor vNext, deze zorgt er voor dat alles wat je nodig hebt om een vNext applicatie te draaien wordt geladen. Ook van KRE kan je verschillende versie hebben en deze kan je ook met het KRE commando managen.

### KLR (K Language Runtime)

KLR is binnen ASP.NET vNext verantwoordelijk voor het aanroepen van de CLR Native Host als vNext in een self hosted enviroment wordt gedraaid (dus niet in IIS bijvoorbeeld) Zie [https://github.com/aspnet/Home/wiki/KRuntime-structure](https://github.com/aspnet/Home/wiki/KRuntime-structure%20) voor meer info

### KPM (K Package Manager)

KPM is verantwoordelijk voor het restoren en installeren van de Packages uit de NuGet repositories. Alles wat met de packages te maken heeft gebeurd via KPM.Zie [https://github.com/aspnet/Home/wiki/Package-Manager](https://github.com/aspnet/Home/wiki/Package-Manager) voor meer informatie

### K

Als je een vNext applicatie wilt draaien gebruik je k run. Voor meer informatie zie [https://github.com/aspnet/Home/wiki/Command-Line](https://github.com/aspnet/Home/wiki/Command-Line) . Eventueel kan er in het project.json bestand nog andere commando's worden opgegeven