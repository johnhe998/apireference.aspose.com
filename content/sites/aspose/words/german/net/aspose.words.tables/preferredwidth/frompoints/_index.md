---
title: PreferredWidth.FromPoints
second_title: Aspose.Words für .NET-API-Referenz
description: PreferredWidth methode. Eine Erstellungsmethode die eine neue Instanz zurückgibt die eine bevorzugte Breite darstellt die durch eine Anzahl von Punkten angegeben wird.
type: docs
weight: 30
url: /de/net/aspose.words.tables/preferredwidth/frompoints/
---
## PreferredWidth.FromPoints method

Eine Erstellungsmethode, die eine neue Instanz zurückgibt, die eine bevorzugte Breite darstellt, die durch eine Anzahl von Punkten angegeben wird.

```csharp
public static PreferredWidth FromPoints(double points)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| points | Double | Der Wert muss zwischen 0 und 22 Zoll liegen (22 * 72 Punkte). |

### Beispiele

Zeigt, wie Einheitenkonvertierungswerkzeuge verwendet werden, während eine bevorzugte Breite für eine Zelle angegeben wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(ConvertUtil.InchToPoint(3));
builder.InsertCell();

Assert.AreEqual(216.0d, table.FirstRow.FirstCell.CellFormat.PreferredWidth.Value);
```

Zeigt, wie Sie eine bevorzugte Breite für Tabellenzellen festlegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Es gibt zwei Möglichkeiten, die Klasse "PreferredWidth" auf Tabellenzellen anzuwenden.
// 1 - Stellen Sie eine absolute bevorzugte Breite basierend auf Punkten ein:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - Legen Sie eine relative bevorzugte Breite basierend auf dem Prozentsatz der Tabellenbreite fest:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// Eine Zelle ohne angegebene bevorzugte Breite nimmt den Rest des verfügbaren Platzes ein.
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// Jede Konfiguration der Eigenschaft "PreferredWidth" erzeugt ein neues Objekt.
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### Siehe auch

* class [PreferredWidth](../)
* namensraum [Aspose.Words.Tables](../../preferredwidth/)
* Montage [Aspose.Words](../../../)


