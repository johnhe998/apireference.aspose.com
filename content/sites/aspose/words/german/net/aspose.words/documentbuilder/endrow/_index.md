---
title: DocumentBuilder.EndRow
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Beendet eine Tabellenzeile im Dokument.
type: docs
weight: 220
url: /de/net/aspose.words/documentbuilder/endrow/
---
## DocumentBuilder.EndRow method

Beendet eine Tabellenzeile im Dokument.

```csharp
public Row EndRow()
```

### Rückgabewert

Der Zeilenknoten, der gerade fertiggestellt wurde.

### Bemerkungen

Anruf **EndRow** um eine Tabellenzeile zu beenden. Wenn Sie anrufen[`InsertCell`](../insertcell/) sofort danach, dann geht die Tabelle in einer neuen Zeile weiter.

Verwenden Sie die[`RowFormat`](../rowformat/) -Eigenschaft zum Angeben der Zeilenformatierung.

### Beispiele

Zeigt, wie Tabellenzellen vertikal verbunden werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Eine Zelle in die erste Spalte der ersten Zeile einfügen.
// Diese Zelle ist die erste in einer Reihe vertikal verbundener Zellen.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Füge eine Zelle in die zweite Spalte der ersten Zeile ein und beende dann die Zeile.
// Konfigurieren Sie außerdem den Builder, um das vertikale Zusammenführen in erstellten Zellen zu deaktivieren.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();

// Eine Zelle in die erste Spalte der zweiten Zeile einfügen. 
// Anstatt Textinhalte hinzuzufügen, werden wir diese Zelle mit der ersten Zelle zusammenführen, die wir direkt darüber hinzugefügt haben.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Eine weitere unabhängige Zelle in die zweite Spalte der zweiten Zeile einfügen.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "CellFormat.VerticalMerge.docx");
```

Zeigt, wie eine formatierte 2x2-Tabelle erstellt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("Row 1, cell 1.");
builder.InsertCell();
builder.Write("Row 1, cell 2.");
builder.EndRow();

// Beim Erstellen der Tabelle wendet der Document Builder seine aktuellen RowFormat/CellFormat-Eigenschaftswerte an
// zur aktuellen Zeile/Zelle, in der sich der Cursor befindet, und zu allen neuen Zeilen/Zellen, wenn sie erstellt werden.
Assert.AreEqual(CellVerticalAlignment.Center, table.Rows[0].Cells[0].CellFormat.VerticalAlignment);
Assert.AreEqual(CellVerticalAlignment.Center, table.Rows[0].Cells[1].CellFormat.VerticalAlignment);

builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Write("Row 2, cell 1.");
builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Write("Row 2, cell 2.");
builder.EndRow();
builder.EndTable();

// Zuvor hinzugefügte Zeilen und Zellen sind nicht rückwirkend von Änderungen an der Formatierung des Builders betroffen.
Assert.AreEqual(0, table.Rows[0].RowFormat.Height);
Assert.AreEqual(HeightRule.Auto, table.Rows[0].RowFormat.HeightRule);
Assert.AreEqual(100, table.Rows[1].RowFormat.Height);
Assert.AreEqual(HeightRule.Exactly, table.Rows[1].RowFormat.HeightRule);
Assert.AreEqual(TextOrientation.Upward, table.Rows[1].Cells[0].CellFormat.Orientation);
Assert.AreEqual(TextOrientation.Downward, table.Rows[1].Cells[1].CellFormat.Orientation);

doc.Save(ArtifactsDir + "DocumentBuilder.BuildTable.docx");
```

Zeigt, wie eine Tabelle mit benutzerdefinierten Rahmen erstellt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();

// Festlegen von Tabellenformatierungsoptionen für einen Dokumentersteller
// wendet sie auf jede Zeile und Zelle an, die wir damit hinzufügen.
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.CellFormat.ClearFormatting();
builder.CellFormat.Width = 150;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.CellFormat.Shading.BackgroundPatternColor = Color.GreenYellow;
builder.CellFormat.WrapText = false;
builder.CellFormat.FitText = true;

builder.RowFormat.ClearFormatting();
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.RowFormat.Height = 50;
builder.RowFormat.Borders.LineStyle = LineStyle.Engrave3D;
builder.RowFormat.Borders.Color = Color.Orange;

builder.InsertCell();
builder.Write("Row 1, Col 1");

builder.InsertCell();
builder.Write("Row 1, Col 2");
builder.EndRow();

// Wenn Sie die Formatierung ändern, wird sie auf die aktuelle Zelle angewendet,
// und alle neuen Zellen, die wir danach mit dem Builder erstellen.
// Dies wirkt sich nicht auf die zuvor hinzugefügten Zellen aus.
builder.CellFormat.Shading.ClearFormatting();

builder.InsertCell();
builder.Write("Row 2, Col 1");

builder.InsertCell();
builder.Write("Row 2, Col 2");

builder.EndRow();

// Erhöhen Sie die Zeilenhöhe, um sie an den vertikalen Text anzupassen.
builder.InsertCell();
builder.RowFormat.Height = 150;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Write("Row 3, Col 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Write("Row 3, Col 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTable.docx");
```

### Siehe auch

* class [Row](../../../aspose.words.tables/row/)
* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


