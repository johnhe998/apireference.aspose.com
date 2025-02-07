---
title: Table.StyleIdentifier
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Ruft den gebietsschemaunabhängigen Stilbezeichner des auf diese Tabelle angewendeten Tabellenstils ab oder legt ihn fest.
type: docs
weight: 280
url: /de/net/aspose.words.tables/table/styleidentifier/
---
## Table.StyleIdentifier property

Ruft den gebietsschemaunabhängigen Stilbezeichner des auf diese Tabelle angewendeten Tabellenstils ab oder legt ihn fest.

```csharp
public StyleIdentifier StyleIdentifier { get; set; }
```

### Beispiele

Zeigt, wie eine neue Tabelle erstellt wird, während ein Stil angewendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Wir müssen mindestens eine Zeile einfügen, bevor wir eine Tabellenformatierung festlegen.
builder.InsertCell();

// Legen Sie den verwendeten Tabellenstil basierend auf der Stilkennung fest.
// Beachten Sie, dass beim Speichern im .doc-Format nicht alle Tabellenstile verfügbar sind.
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;

// Wenden Sie den Stil teilweise auf Features der Tabelle an, basierend auf Prädikaten, und erstellen Sie dann die Tabelle.
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

### Siehe auch

* enum [StyleIdentifier](../../../aspose.words/styleidentifier/)
* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


