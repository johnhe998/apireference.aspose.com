---
title: Class Shading
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Shading klas. Enthält Schattierungsattribute für ein Objekt.
type: docs
weight: 5690
url: /de/net/aspose.words/shading/
---
## Shading class

Enthält Schattierungsattribute für ein Objekt.

```csharp
public class Shading : InternableComplexAttr
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [BackgroundPatternColor](../../aspose.words/shading/backgroundpatterncolor/) { get; set; } | Ruft die Farbe ab oder legt sie fest, die auf den Hintergrund des Shading-Objekts angewendet wird. |
| [ForegroundPatternColor](../../aspose.words/shading/foregroundpatterncolor/) { get; set; } | Ruft die Farbe ab oder legt sie fest, die auf den Vordergrund des Shading-Objekts angewendet wird. |
| [Texture](../../aspose.words/shading/texture/) { get; set; } | Ruft die Schattierungstextur ab oder legt sie fest. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [ClearFormatting](../../aspose.words/shading/clearformatting/)() | Entfernt die Schattierung vom Objekt. |
| override [Equals](../../aspose.words/shading/equals/#equals_1)(object) | Bestimmt, ob das angegebene Objekt im Wert dem aktuellen Objekt entspricht. |
| [Equals](../../aspose.words/shading/equals/#equals)(Shading) | Bestimmt, ob die angegebene Schattierung im Wert der aktuellen Schattierung entspricht. |
| override [GetHashCode](../../aspose.words/shading/gethashcode/)() | Dient als Hash-Funktion für diesen Typ. |

### Beispiele

Zeigt, wie Text mit Rändern und Schattierungen verziert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;

Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = Color.LightCoral;
shading.ForegroundPatternColor = Color.LightSalmon;

builder.Write("This paragraph is formatted with a double border and shading.");
doc.Save(ArtifactsDir + "DocumentBuilder.ApplyBordersAndShading.docx");
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

* class [InternableComplexAttr](../internablecomplexattr/)
* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


