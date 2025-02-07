---
title: Cell.EnsureMinimum
second_title: Aspose.Words für .NET-API-Referenz
description: Cell methode. Wenn das letzte untergeordnete Element kein Absatz ist wird ein leerer Absatz erstellt und angehängt.
type: docs
weight: 120
url: /de/net/aspose.words.tables/cell/ensureminimum/
---
## Cell.EnsureMinimum method

Wenn das letzte untergeordnete Element kein Absatz ist, wird ein leerer Absatz erstellt und angehängt.

```csharp
public void EnsureMinimum()
```

### Beispiele

Zeigt, wie sichergestellt wird, dass ein Zellknoten die Knoten enthält, die wir benötigen, um mit dem Hinzufügen von Inhalten zu beginnen.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
Row row = new Row(doc);
table.AppendChild(row);
Cell cell = new Cell(doc);
row.AppendChild(cell);

// Zellen können Absätze mit typischen Elementen wie Läufen, Formen und sogar anderen Tabellen enthalten.
// Unsere neue Zelle hat keine Absätze, und wir können ihr keine Inhalte wie Lauf- und Formknoten hinzufügen, bis dies der Fall ist.
Assert.AreEqual(0, cell.GetChildNodes(NodeType.Any, true).Count);

// Das Aufrufen der "EnsureMinimum"-Methode für eine Zelle stellt dies sicher
// Die Zelle hat mindestens einen leeren Absatz, dem wir dann Inhalte hinzufügen können.
cell.EnsureMinimum();
cell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### Siehe auch

* class [Cell](../)
* namensraum [Aspose.Words.Tables](../../cell/)
* Montage [Aspose.Words](../../../)


