---
title: Class TextColumn
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.TextColumn klass. Representerar en enda textkolumn. Textkolumn är medlem iTextColumnCollection samling. Den Textkolumner samlingen innehåller alla kolumner i ett avsnitt av ett dokument.
type: docs
weight: 6090
url: /sv/net/aspose.words/textcolumn/
---
## TextColumn class

Representerar en enda textkolumn. **Textkolumn** är medlem i[`TextColumnCollection`](../textcolumncollection/) samling. Den **Textkolumner** samlingen innehåller alla kolumner i ett avsnitt av ett dokument.

```csharp
public class TextColumn
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [SpaceAfter](../../aspose.words/textcolumn/spaceafter/) { get; set; } | Hämtar eller ställer in utrymmet mellan denna kolumn och nästa kolumn i poäng. Krävs inte för den sista kolumnen. |
| [Width](../../aspose.words/textcolumn/width/) { get; set; } | Hämtar eller ställer in bredden på textkolumnen i punkter. |

### Anmärkningar

**Textkolumn** objekt används endast för att ange kolumner med anpassad bredd och avstånd. Om du vill att kolumnerna i dokumentet ska vara lika breda, ställ in TextColumns.[`EvenlySpaced`](../textcolumncollection/evenlyspaced/) till **Sann**.

När en ny **Textkolumn** skapas har dess bredd och avstånd noll.

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

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


