---
title: Table.StyleOptions
second_title: Aspose.Words för .NET API Referens
description: Table fast egendom. Hämtar eller ställer in bitflaggor som anger hur en tabellstil tillämpas på den här tabellen.
type: docs
weight: 300
url: /sv/net/aspose.words.tables/table/styleoptions/
---
## Table.StyleOptions property

Hämtar eller ställer in bitflaggor som anger hur en tabellstil tillämpas på den här tabellen.

```csharp
public TableStyleOptions StyleOptions { get; set; }
```

### Exempel

Visar hur man bygger en ny tabell samtidigt som man använder en stil.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Vi måste infoga minst en rad innan vi ställer in någon tabellformatering.
builder.InsertCell();

// Ställ in tabellstilen som används baserat på stilidentifieraren.
// Observera att inte alla tabellstilar är tillgängliga när du sparar i .doc-format.
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;

// Tillämpa stilen delvis på funktioner i tabellen baserat på predikat, bygg sedan tabellen.
table.StyleOptions =
    TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
table.AutoFit(AutoFitBehavior.AutoFitToContents);

builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writeln("Quantity (kg)");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writeln("40");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableWithStyle.docx");
```

### Se även

* enum [TableStyleOptions](../../tablestyleoptions/)
* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


