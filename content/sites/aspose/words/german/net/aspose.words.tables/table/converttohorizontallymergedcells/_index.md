---
title: Table.ConvertToHorizontallyMergedCells
second_title: Aspose.Words für .NET-API-Referenz
description: Table methode. Konvertiert Zellen die horizontal nach Breite verbunden sind in Zellen die nach verbunden sindHorizontalMerge .
type: docs
weight: 390
url: /de/net/aspose.words.tables/table/converttohorizontallymergedcells/
---
## Table.ConvertToHorizontallyMergedCells method

Konvertiert Zellen, die horizontal nach Breite verbunden sind, in Zellen, die nach verbunden sind[`HorizontalMerge`](../../cellformat/horizontalmerge/) .

```csharp
public void ConvertToHorizontallyMergedCells()
```

### Bemerkungen

Tabellenzellen können horizontal zusammengeführt werden, indem Sie Merge-Flags verwenden[`HorizontalMerge`](../../cellformat/horizontalmerge/) oder mit Zellenbreite[`Width`](../../cellformat/width/).

Wenn die Tabellenzelle durch die Breiteneigenschaft zusammengeführt wird[`HorizontalMerge`](../../cellformat/horizontalmerge/) ist bedeutungslos, aber manchmal ist es bequemer, Merge-Flags zu haben.

Verwenden Sie diese Methode, um horizontal nach Breite verbundene Tabellenzellen in Zellen umzuwandeln, die durch Merge-Flags verbunden sind.

### Beispiele

Zeigt, wie horizontal verbundene Zellen nach Breite in Zellen konvertiert werden, die durch CellFormat.HorizontalMerge verbunden wurden.

```csharp
Document doc = new Document(MyDir + "Table with merged cells.docx");

// Microsoft Word schreibt keine Merge-Flags mehr und definiert stattdessen verbundene Zellen nach Breite.
// Aspose.Words definiert standardmäßig nur 5 Zellen in einer Reihe, und keine von ihnen hat das horizontale Merge-Flag,
// obwohl es 7 Zellen in der Zeile gab, bevor die horizontale Zusammenführung stattfand.
Table table = doc.FirstSection.Body.Tables[0];
Row row = table.Rows[0];

Assert.AreEqual(5, row.Cells.Count);
Assert.True(row.Cells.All(c => ((Cell)c).CellFormat.HorizontalMerge == CellMerge.None));

// Verwenden Sie die Methode "ConvertToHorizontallyMergedCells", um horizontal verbundene Zellen zu konvertieren
// durch seine Breite zu der durch Flags horizontal zusammengeführten Zelle.
// Jetzt haben wir 7 Zellen und einige von ihnen haben horizontale Zusammenführungswerte.
table.ConvertToHorizontallyMergedCells();
row = table.Rows[0];

Assert.AreEqual(7, row.Cells.Count);

Assert.AreEqual(CellMerge.None, row.Cells[0].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.First, row.Cells[1].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.Previous, row.Cells[2].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.None, row.Cells[3].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.First, row.Cells[4].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.Previous, row.Cells[5].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.None, row.Cells[6].CellFormat.HorizontalMerge);
```

### Siehe auch

* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


