---
title: Table.AllowCellSpacing
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Ruft die Option Abstände zwischen Zellen zulassen ab oder legt sie fest.
type: docs
weight: 60
url: /de/net/aspose.words.tables/table/allowcellspacing/
---
## Table.AllowCellSpacing property

Ruft die Option "Abstände zwischen Zellen zulassen" ab oder legt sie fest.

```csharp
public bool AllowCellSpacing { get; set; }
```

### Beispiele

Zeigt, wie Sie den Abstand zwischen einzelnen Zellen in einer Tabelle aktivieren.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Animal");
builder.InsertCell();
builder.Write("Class");
builder.EndRow();
builder.InsertCell();
builder.Write("Dog");
builder.InsertCell();
builder.Write("Mammal");
builder.EndTable();

table.CellSpacing = 3;

// Setzen Sie die Eigenschaft "AllowCellSpacing" auf "true", um den Abstand zwischen den Zellen zu aktivieren
// mit einer Größe, die dem Wert der Eigenschaft "CellSpacing" in Punkten entspricht.
// Setzen Sie die Eigenschaft "AllowCellSpacing" auf "false", um den Zellabstand zu deaktivieren
// und den Wert der Eigenschaft "CellSpacing" ignorieren.
table.AllowCellSpacing = allowCellSpacing;

doc.Save(ArtifactsDir + "Table.AllowCellSpacing.html");

// Das Anpassen der Eigenschaft "CellSpacing" aktiviert automatisch den Zellabstand.
table.CellSpacing = 5;

Assert.True(table.AllowCellSpacing);
```

### Siehe auch

* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


