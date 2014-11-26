title: "Nieuwe features in C# 6.0"
date: 2014-11-21 22:31:04
tags:
  - .NET
  - Microsoft
  - vNext
  - "C#"
categories:
  - ASP.NET vNext
  - Coding
  - Microsoft
---
Met de release van [ASP.NET vNext](http://www.asp.net/vnext) heeft Microsoft ook een nieuwe versie van de [C#](http://en.wikipedia.org/wiki/C_Sharp_(programming_language)) programmeer taal aangekondigd. Inmiddels zijn we bij versie 6.0 van C# aangekomen (niet verwarren met de versienummers van het .NET framework). In vergelijking met eerdere versies bevat versie 6.0 maar weinig echte grote verbeteringen en Microsoft heeft vooral veel tijd in vNext en Roslyn gestoken. Verwacht dus geen nieuwe features die net zoveel impact hebben als Linq of Generics maar veelal verfijning van de taal C#.

Wat is er dan wel veranderd?

<!-- more -->
*Auto-property initializers* bestaan nu ook in C# en zijn vergelijkbaar met het automatisch zetten van velden
```
public class Product {
    public string ProductNaam {get; set; } = "Motorolie";
}
```

Dit werkt nu ook voor *Getter-only auto-properties*
```
public class Product {
    public string ProductNaam {get;} = "Motorolie";
}
```

*nameof Expression* is een nieuwe string functie welke de mogelijkheid geeft om bijvoorbeeld de naam van een Property kan retourneren. Uiteraard kan je dit ook handmatig zetten maar met de nameof expression kan je dit met de compiler afdwingen wat het refactoren weer makkelijk maakt.
```
Console.WrileLine(nameof(Product.ProductNaam));  //output: ProductNaam
```

*String interpolation* maakt String.Format overbodig waar je voorheen
```
String.Format("Hallo {0}, het is vandaag {1}", naam, DateTime.Now.Date);
```
moest gebruiken kan je het tegenwoordig af met
```
var tekst = "Hallo \{naam}, het is vandaag \{DateTime.Now.Date}";
```

*Null-conditional operators* maakt code overzichtelijker door het eindeloze null-checken te vereenvoudigen. Waar je voorheen
```
int? nummer = product != null ? product.nummer : (int?)null;
```
moest gebruiken om geen Nullpointer exeption te krijgen kan je dit nu oplossen door *.?* te gebruiken
```
int? nummer = product.?nummer;
```

*Index initializers* zijn uitgebreid zodat je nu niet alleen Member variabelen kan initialiseren maar ook de indices van het nieuw aangemaakte object.
```
var producten = new Dictionary<int, Product> {
[2] = new Product(),
[11] = Product()
}
``` 

Nog een leuke feature is *Expression-bodied function members*, deze maken het mogelijk om methods, properties en andere functionmembers in een expressie te stoppen in plaats van een statement block
```
public int Optellen(int i, int j) => i + j;
```
Hiermee kan je ook andere methodes aanroepen, bijvoorbeeld
```
public void Print(string bericht) => Console.WriteLine(bericht);
```

Naast *paramterless constructors* in een class kan je deze nu ook gebruiken in een struct. Verder kan nu ook met *using static* methodes aanroepen zonder de hele class op te geven. Ook zijn *Exception filters* en *await in catch en finally blocks* toegevoegd aan C# 6.0