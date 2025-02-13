---
title: Table.RelativeHorizontalAlignment
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Ruft die relative horizontale Ausrichtung der FloatingTabelle ab oder legt sie fest.
type: docs
weight: 230
url: /de/net/aspose.words.tables/table/relativehorizontalalignment/
---
## Table.RelativeHorizontalAlignment property

Ruft die relative horizontale Ausrichtung der Floating-Tabelle ab oder legt sie fest.

```csharp
public HorizontalAlignment RelativeHorizontalAlignment { get; set; }
```

### Beispiele

Zeigt, wie die Position von Floating-Tabellen festgelegt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 1, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// Setzen Sie die Position der Tabelle auf eine Stelle auf der Seite, wie in diesem Fall die untere rechte Ecke.
table.RelativeVerticalAlignment = VerticalAlignment.Bottom;
table.RelativeHorizontalAlignment = HorizontalAlignment.Right;

table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 2, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// Wir können auch einen horizontalen und vertikalen Abstand in Punkten von der Position des Absatzes festlegen, an der wir die Tabelle eingefügt haben. 
table.AbsoluteVerticalDistance = 50;
table.AbsoluteHorizontalDistance = 100;

doc.Save(ArtifactsDir + "Table.ChangeFloatingTableProperties.docx");
```

### Siehe auch

* enum [HorizontalAlignment](../../../aspose.words.drawing/horizontalalignment/)
* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


