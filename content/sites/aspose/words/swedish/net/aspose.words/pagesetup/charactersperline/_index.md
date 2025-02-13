---
title: PageSetup.CharactersPerLine
second_title: Aspose.Words för .NET API Referens
description: PageSetup fast egendom. Hämtar eller ställer in antalet tecken per rad i dokumentrutnätet.
type: docs
weight: 100
url: /sv/net/aspose.words/pagesetup/charactersperline/
---
## PageSetup.CharactersPerLine property

Hämtar eller ställer in antalet tecken per rad i dokumentrutnätet.

```csharp
public int CharactersPerLine { get; set; }
```

### Anmärkningar

Minsta värde för egenskapen är 1. Maximalt värde beror på sidbredden och teckenstorleken för stilen Normal . Minsta teckenbredd är 90 procent av teckenstorleken. Till exempel är det maximala antalet tecken per rad på en Letter-sida med en tums marginaler 43.

Som standard har egenskapen ett värde där teckenbredden är lika med teckenstorleken i stilen Normal .

### Exempel

Visar hur man anger a för antalet tecken som varje rad kan ha.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aktivera pitching och använd den sedan för att ställa in antalet tecken per rad i det här avsnittet.
builder.PageSetup.LayoutMode = SectionLayoutMode.Grid;
builder.PageSetup.CharactersPerLine = 10;

// Antalet tecken beror också på storleken på teckensnittet.
doc.Styles["Normal"].Font.Size = 20;

Assert.AreEqual(8, doc.FirstSection.PageSetup.CharactersPerLine);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "PageSetup.CharactersPerLine.docx");
```

### Se även

* class [PageSetup](../)
* namnutrymme [Aspose.Words](../../pagesetup/)
* hopsättning [Aspose.Words](../../../)


