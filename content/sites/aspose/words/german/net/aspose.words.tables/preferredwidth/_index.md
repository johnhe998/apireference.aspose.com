---
title: Class PreferredWidth
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Tables.PreferredWidth klas. Stellt einen Wert und seine Maßeinheit dar die verwendet wird um die bevorzugte Breite einer Tabelle oder Zelle anzugeben.
type: docs
weight: 5990
url: /de/net/aspose.words.tables/preferredwidth/
---
## PreferredWidth class

Stellt einen Wert und seine Maßeinheit dar, die verwendet wird, um die bevorzugte Breite einer Tabelle oder Zelle anzugeben.

```csharp
public sealed class PreferredWidth
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Type](../../aspose.words.tables/preferredwidth/type/) { get; } | Ruft die Maßeinheit ab, die für diesen bevorzugten Breitenwert verwendet wird. |
| [Value](../../aspose.words.tables/preferredwidth/value/) { get; } | Ruft den bevorzugten Breitenwert ab. Die Maßeinheit ist in der angegeben[`Type`](./type/) Eigentum. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| static [FromPercent](../../aspose.words.tables/preferredwidth/frompercent/)(double) | Eine Erstellungsmethode, die eine neue Instanz zurückgibt, die eine als Prozentsatz angegebene bevorzugte Breite darstellt. |
| static [FromPoints](../../aspose.words.tables/preferredwidth/frompoints/)(double) | Eine Erstellungsmethode, die eine neue Instanz zurückgibt, die eine bevorzugte Breite darstellt, die durch eine Anzahl von Punkten angegeben wird. |
| override [Equals](../../aspose.words.tables/preferredwidth/equals/#equals_1)(object) | Bestimmt, ob das angegebene Objekt im Wert dem aktuellen Objekt entspricht. |
| [Equals](../../aspose.words.tables/preferredwidth/equals/#equals)(PreferredWidth) | Bestimmt, ob die angegebene PreferredWidth im Wert der aktuellen PreferredWidth entspricht. |
| override [GetHashCode](../../aspose.words.tables/preferredwidth/gethashcode/)() | dient als Hash-Funktion für diesen Typ. |
| override [ToString](../../aspose.words.tables/preferredwidth/tostring/)() | Gibt eine benutzerfreundliche Zeichenfolge zurück, die den Wert dieses Objekts anzeigt. |

## Felder

| Name | Beschreibung |
| --- | --- |
| static readonly [Auto](../../aspose.words.tables/preferredwidth/auto/) | Gibt eine Instanz zurück, die den Wert „Bevorzugte Breite ist nicht angegeben“ darstellt. |

### Bemerkungen

Die bevorzugte Breite kann als Prozentzahl, Punktzahl oder als spezieller "none/auto"-Wert angegeben werden.

Die Instanzen dieser Klasse sind unveränderlich.

### Beispiele

Zeigt, wie eine Tabelle so eingestellt wird, dass sie automatisch an 50 % der Seitenbreite angepasst wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell #1");
builder.InsertCell();
builder.Write("Cell #2");
builder.InsertCell();
builder.Write("Cell #3");

table.PreferredWidth = PreferredWidth.FromPercent(50);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableWithPreferredWidth.docx");
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

* namensraum [Aspose.Words.Tables](../../aspose.words.tables/)
* Montage [Aspose.Words](../../)


