---
title: CellFormat.LeftPadding
second_title: Aspose.Words für .NET-API-Referenz
description: CellFormat eigendom. Gibt den Abstand in Punkten zurück oder legt ihn fest der links vom Inhalt der Zelle hinzugefügt werden soll.
type: docs
weight: 50
url: /de/net/aspose.words.tables/cellformat/leftpadding/
---
## CellFormat.LeftPadding property

Gibt den Abstand (in Punkten) zurück oder legt ihn fest, der links vom Inhalt der Zelle hinzugefügt werden soll.

```csharp
public double LeftPadding { get; set; }
```

### Beispiele

Zeigt, wie Zellen mit einem Document Builder formatiert werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, cell 1.");

// Eine zweite Zelle einfügen und dann Optionen zum Auffüllen des Zelltextes konfigurieren.
// Der Builder wendet diese Einstellungen auf seine aktuelle Zelle an und erstellt danach alle neuen Zellen.
builder.InsertCell();

CellFormat cellFormat = builder.CellFormat;
cellFormat.Width = 250;
cellFormat.LeftPadding = 30;
cellFormat.RightPadding = 30;
cellFormat.TopPadding = 30;
cellFormat.BottomPadding = 30;

builder.Write("Row 1, cell 2.");
builder.EndRow();
builder.EndTable();

// Die erste Zelle war von der Padding-Neukonfiguration nicht betroffen und enthält immer noch die Standardwerte.
Assert.AreEqual(0.0d, table.FirstRow.Cells[0].CellFormat.Width);
Assert.AreEqual(5.4d, table.FirstRow.Cells[0].CellFormat.LeftPadding);
Assert.AreEqual(5.4d, table.FirstRow.Cells[0].CellFormat.RightPadding);
Assert.AreEqual(0.0d, table.FirstRow.Cells[0].CellFormat.TopPadding);
Assert.AreEqual(0.0d, table.FirstRow.Cells[0].CellFormat.BottomPadding);

Assert.AreEqual(250.0d, table.FirstRow.Cells[1].CellFormat.Width);
Assert.AreEqual(30.0d, table.FirstRow.Cells[1].CellFormat.LeftPadding);
Assert.AreEqual(30.0d, table.FirstRow.Cells[1].CellFormat.RightPadding);
Assert.AreEqual(30.0d, table.FirstRow.Cells[1].CellFormat.TopPadding);
Assert.AreEqual(30.0d, table.FirstRow.Cells[1].CellFormat.BottomPadding);

// Die erste Zelle wird im Ausgabedokument immer noch größer, um sie an die Größe der benachbarten Zelle anzupassen.
doc.Save(ArtifactsDir + "DocumentBuilder.SetCellFormatting.docx");
```

### Siehe auch

* class [CellFormat](../)
* namensraum [Aspose.Words.Tables](../../cellformat/)
* Montage [Aspose.Words](../../../)


