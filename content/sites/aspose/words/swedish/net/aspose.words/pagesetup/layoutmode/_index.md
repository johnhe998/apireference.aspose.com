---
title: PageSetup.LayoutMode
second_title: Aspose.Words för .NET API Referens
description: PageSetup fast egendom. Hämtar eller ställer in layoutläget för detta avsnitt.
type: docs
weight: 190
url: /sv/net/aspose.words/pagesetup/layoutmode/
---
## PageSetup.LayoutMode property

Hämtar eller ställer in layoutläget för detta avsnitt.

```csharp
public SectionLayoutMode LayoutMode { get; set; }
```

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

Visar hur man anger en gräns för antalet rader som varje sida kan ha.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aktivera pitching och använd den sedan för att ställa in antalet rader per sida i det här avsnittet.
// En tillräckligt stor teckenstorlek kommer att trycka ner några rader till nästa sida för att undvika överlappande tecken.
builder.PageSetup.LayoutMode = SectionLayoutMode.LineGrid;
builder.PageSetup.LinesPerPage = 15;

builder.ParagraphFormat.SnapToGrid = true;

for (int i = 0; i < 30; i++)
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. ");

doc.Save(ArtifactsDir + "PageSetup.LinesPerPage.docx");
```

### Se även

* enum [SectionLayoutMode](../../sectionlayoutmode/)
* class [PageSetup](../)
* namnutrymme [Aspose.Words](../../pagesetup/)
* hopsättning [Aspose.Words](../../../)


