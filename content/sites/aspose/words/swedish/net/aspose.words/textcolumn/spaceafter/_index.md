---
title: TextColumn.SpaceAfter
second_title: Aspose.Words för .NET API Referens
description: TextColumn fast egendom. Hämtar eller ställer in utrymmet mellan denna kolumn och nästa kolumn i poäng. Krävs inte för den sista kolumnen.
type: docs
weight: 10
url: /sv/net/aspose.words/textcolumn/spaceafter/
---
## TextColumn.SpaceAfter property

Hämtar eller ställer in utrymmet mellan denna kolumn och nästa kolumn i poäng. Krävs inte för den sista kolumnen.

```csharp
public double SpaceAfter { get; set; }
```

### Exempel

Visar hur man skapar ojämnt fördelade kolumner.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
PageSetup pageSetup = builder.PageSetup;

TextColumnCollection columns = pageSetup.TextColumns;
columns.EvenlySpaced = false;
columns.SetCount(2);

// Bestäm mängden utrymme som vi har tillgängligt för att arrangera kolumner.
double contentWidth = pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin;

Assert.AreEqual(470.30d, contentWidth, 0.01d);

// Ange att den första kolumnen ska vara smal.
TextColumn column = columns[0];
column.Width = 100;
column.SpaceAfter = 20;

// Ställ in den andra kolumnen för att ta resten av det tillgängliga utrymmet inom sidans marginaler.
column = columns[1];
column.Width = contentWidth - column.Width - column.SpaceAfter;

builder.Writeln("Narrow column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Wide column 2.");

doc.Save(ArtifactsDir + "PageSetup.CustomColumnWidth.docx");
```

### Se även

* class [TextColumn](../)
* namnutrymme [Aspose.Words](../../textcolumn/)
* hopsättning [Aspose.Words](../../../)


