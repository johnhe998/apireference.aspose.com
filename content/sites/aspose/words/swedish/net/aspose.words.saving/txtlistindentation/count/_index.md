---
title: TxtListIndentation.Count
second_title: Aspose.Words för .NET API Referens
description: TxtListIndentation fast egendom. Hämtar eller ställer in hur mångaCharacter att använda som indrag per en listnivå. Standardvärdet är 0 det betyder ingen indrag.
type: docs
weight: 30
url: /sv/net/aspose.words.saving/txtlistindentation/count/
---
## TxtListIndentation.Count property

Hämtar eller ställer in hur många[`Character`](../character/) att använda som indrag per en listnivå. Standardvärdet är 0, det betyder ingen indrag.

```csharp
public int Count { get; set; }
```

### Exempel

Visar hur du konfigurerar listindrag när du sparar ett dokument som klartext.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en lista med tre nivåer av indrag.
builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.ListFormat.ListIndent();
builder.Writeln("Item 2");
builder.ListFormat.ListIndent(); 
builder.Write("Item 3");

// Skapa ett "TxtSaveOptions"-objekt, som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur vi sparar dokumentet som klartext.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// Ställ in egenskapen "Character" för att tilldela ett tecken att använda
// för utfyllnad som simulerar listindrag i klartext.
txtSaveOptions.ListIndentation.Character = ' ';

// Ställ in egenskapen "Count" för att ange antalet gånger
// för att placera utfyllnadstecknet för varje listindragsnivå.
txtSaveOptions.ListIndentation.Count = 3;

doc.Save(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt");

Assert.AreEqual("1. Item 1\r\n" +
                "   a. Item 2\r\n" +
                "      i. Item 3\r\n", docText);
```

### Se även

* class [TxtListIndentation](../)
* namnutrymme [Aspose.Words.Saving](../../txtlistindentation/)
* hopsättning [Aspose.Words](../../../)


