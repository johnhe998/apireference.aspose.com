---
title: Table.SetBorders
second_title: Aspose.Words für .NET-API-Referenz
description: Table methode. Setzt alle Tabellenrahmen auf den angegebenen Linienstil Breite und Farbe.
type: docs
weight: 420
url: /de/net/aspose.words.tables/table/setborders/
---
## Table.SetBorders method

Setzt alle Tabellenrahmen auf den angegebenen Linienstil, Breite und Farbe.

```csharp
public void SetBorders(LineStyle lineStyle, double lineWidth, Color color)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| lineStyle | LineStyle | Der anzuwendende Linienstil. |
| lineWidth | Double | Die festzulegende Linienbreite (in Punkten). |
| color | Color | Die für den Rahmen zu verwendende Farbe. |

### Beispiele

Zeigt, wie alle Rahmen einer Tabelle gleichzeitig formatiert werden.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Alle vorhandenen Grenzen aus der Tabelle löschen.
table.ClearBorders();

// Legen Sie eine einzelne grüne Linie fest, die als äußerer und innerer Rand dieser Tabelle dient.
table.SetBorders(LineStyle.Single, 1.5, Color.Green);

doc.Save(ArtifactsDir + "Table.SetBorders.docx");
```

Zeigt, wie Sie Rahmen- und Schattierungsfarbe beim Erstellen einer Tabelle anwenden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Beginne eine Tabelle und setze eine Standardfarbe/Dicke für ihre Ränder.
Table table = builder.StartTable();
table.SetBorders(LineStyle.Single, 2.0, Color.Black);

// Erstellen Sie eine Zeile mit zwei Zellen mit unterschiedlichen Hintergrundfarben.
builder.InsertCell();
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightSkyBlue;
builder.Writeln("Row 1, Cell 1.");
builder.InsertCell();
builder.CellFormat.Shading.BackgroundPatternColor = Color.Orange;
builder.Writeln("Row 1, Cell 2.");
builder.EndRow();

// Zellenformatierung zurücksetzen, um die Hintergrundfarben zu deaktivieren
// Legen Sie eine benutzerdefinierte Rahmenstärke für alle neuen Zellen fest, die vom Builder erstellt wurden.
// Dann baue eine zweite Reihe.
builder.CellFormat.ClearFormatting();
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;

builder.InsertCell();
builder.Writeln("Row 2, Cell 1.");
builder.InsertCell();
builder.Writeln("Row 2, Cell 2.");

doc.Save(ArtifactsDir + "DocumentBuilder.TableBordersAndShading.docx");
```

### Siehe auch

* enum [LineStyle](../../../aspose.words/linestyle/)
* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


