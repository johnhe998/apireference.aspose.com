---
title: NodeList.Count
second_title: Aspose.Words för .NET API Referens
description: NodeList fast egendom. Hämtar antalet noder i listan.
type: docs
weight: 10
url: /sv/net/aspose.words/nodelist/count/
---
## NodeList.Count property

Hämtar antalet noder i listan.

```csharp
public int Count { get; }
```

### Exempel

Visar hur man använder XPaths för att navigera i en nodlista.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga några noder med en DocumentBuilder.
builder.Writeln("Hello world!");

builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();

#if NET48 || JAVA
builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
#elif NET5_0_OR_GREATER || __MOBILE__
using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
    builder.InsertImage(image);
#endif

// Vårt dokument innehåller tre Run-noder.
NodeList nodeList = doc.SelectNodes("//Springa");

Assert.AreEqual(3, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Hello world!"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// Använd ett dubbelt snedstreck för att välja alla Run-noder
// som är indirekta avkomlingar till en tabellnod, vilket skulle vara körningarna inuti de två cellerna vi infogade.
nodeList = doc.SelectNodes("//Table//Springa");

Assert.AreEqual(2, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// Enkla snedstreck anger direkta efterkommande relationer,
// som vi hoppade över när vi använde dubbla snedstreck.
Assert.AreEqual(doc.SelectNodes("  //Table//Kör"),
    doc.SelectNodes("//Tabell/Rad/Cell/Paragraph/Run"));

// Gå till formen som innehåller bilden vi infogade.
nodeList = doc.SelectNodes("//Form");

Assert.AreEqual(1, nodeList.Count);

Shape shape = (Shape)nodeList[0];
Assert.True(shape.HasImage);
```

### Se även

* class [NodeList](../)
* namnutrymme [Aspose.Words](../../nodelist/)
* hopsättning [Aspose.Words](../../../)


