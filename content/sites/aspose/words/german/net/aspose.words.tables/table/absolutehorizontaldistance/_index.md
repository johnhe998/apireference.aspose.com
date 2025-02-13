---
title: Table.AbsoluteHorizontalDistance
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Ermittelt oder setzt die absolute horizontale Position der schwebenden Tabelle die durch die Tabelleneigenschaften angegeben ist in Punkten. Der Standardwert ist 0.
type: docs
weight: 20
url: /de/net/aspose.words.tables/table/absolutehorizontaldistance/
---
## Table.AbsoluteHorizontalDistance property

Ermittelt oder setzt die absolute horizontale Position der schwebenden Tabelle, die durch die Tabelleneigenschaften angegeben ist, in Punkten. Der Standardwert ist 0.

```csharp
public double AbsoluteHorizontalDistance { get; set; }
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

* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


