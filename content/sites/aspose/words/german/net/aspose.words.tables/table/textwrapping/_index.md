---
title: Table.TextWrapping
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Holt oder setztTextWrapping für Tabelle.
type: docs
weight: 310
url: /de/net/aspose.words.tables/table/textwrapping/
---
## Table.TextWrapping property

Holt oder setzt`TextWrapping` für Tabelle.

```csharp
public TextWrapping TextWrapping { get; set; }
```

### Beispiele

Zeigt, wie Sie mit Tabellentextumbruch arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

builder.Font.Size = 16;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Setzen Sie die "TextWrapping"-Eigenschaft auf "TextWrapping.Around", damit die Tabelle Text um sie herumfließt,
// und schieben Sie es in den folgenden Absatz, indem Sie die Position festlegen.
table.TextWrapping = TextWrapping.Around;
table.AbsoluteHorizontalDistance = 100;
table.AbsoluteVerticalDistance = 20;

doc.Save(ArtifactsDir + "Table.WrapText.docx");
```

### Siehe auch

* enum [TextWrapping](../../textwrapping/)
* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


