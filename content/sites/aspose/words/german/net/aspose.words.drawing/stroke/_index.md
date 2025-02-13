---
title: Class Stroke
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.Stroke klas. Definiert einen Strich für eine Form.
type: docs
weight: 1160
url: /de/net/aspose.words.drawing/stroke/
---
## Stroke class

Definiert einen Strich für eine Form.

```csharp
public class Stroke
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [BackColor](../../aspose.words.drawing/stroke/backcolor/) { get; set; } | Ruft die Hintergrundfarbe des Strichs ab oder legt sie fest. |
| [Color](../../aspose.words.drawing/stroke/color/) { get; set; } | Definiert die Farbe eines Strichs. |
| [Color2](../../aspose.words.drawing/stroke/color2/) { get; set; } | Definiert eine zweite Farbe für einen Strich. |
| [DashStyle](../../aspose.words.drawing/stroke/dashstyle/) { get; set; } | Gibt das Punkt- und Strichmuster für einen Strich an. |
| [EndArrowLength](../../aspose.words.drawing/stroke/endarrowlength/) { get; set; } | Definiert die Pfeilspitzenlänge für das Ende eines Strichs. |
| [EndArrowType](../../aspose.words.drawing/stroke/endarrowtype/) { get; set; } | Definiert die Pfeilspitze für das Ende eines Strichs. |
| [EndArrowWidth](../../aspose.words.drawing/stroke/endarrowwidth/) { get; set; } | Definiert die Pfeilspitzenbreite für das Ende eines Strichs. |
| [EndCap](../../aspose.words.drawing/stroke/endcap/) { get; set; } | Definiert den Abschlussstil für das Ende eines Strichs. |
| [ForeColor](../../aspose.words.drawing/stroke/forecolor/) { get; set; } | Ruft die Vordergrundfarbe des Strichs ab oder legt sie fest. |
| [ImageBytes](../../aspose.words.drawing/stroke/imagebytes/) { get; } | Definiert das Bild für ein Strichbild oder eine Musterfüllung. |
| [JoinStyle](../../aspose.words.drawing/stroke/joinstyle/) { get; set; } | Definiert den Verbindungsstil einer Polylinie. |
| [LineStyle](../../aspose.words.drawing/stroke/linestyle/) { get; set; } | Definiert den Linienstil des Strichs. |
| [On](../../aspose.words.drawing/stroke/on/) { get; set; } | Definiert, ob der Pfad gestrichelt wird. |
| [Opacity](../../aspose.words.drawing/stroke/opacity/) { get; set; } | Definiert die Transparenz eines Strichs. Der gültige Bereich liegt zwischen 0 und 1. |
| [StartArrowLength](../../aspose.words.drawing/stroke/startarrowlength/) { get; set; } | Definiert die Pfeilspitzenlänge für den Beginn eines Strichs. |
| [StartArrowType](../../aspose.words.drawing/stroke/startarrowtype/) { get; set; } | Definiert die Pfeilspitze für den Anfang eines Strichs. |
| [StartArrowWidth](../../aspose.words.drawing/stroke/startarrowwidth/) { get; set; } | Definiert die Pfeilspitzenbreite für den Anfang eines Strichs. |
| [Transparency](../../aspose.words.drawing/stroke/transparency/) { get; set; } | Ruft einen Wert zwischen 0,0 (undurchsichtig) und 1,0 (klar) ab oder legt ihn fest, der den Transparenzgrad des Strichs darstellt. |
| [Visible](../../aspose.words.drawing/stroke/visible/) { get; set; } | Ruft ein Flag ab oder setzt es, das angibt, ob der Strich sichtbar ist. |
| [Weight](../../aspose.words.drawing/stroke/weight/) { get; set; } | Definiert die Pinselstärke, die den Pfad einer Form in Punkten streicht. |

### Bemerkungen

Verwenden Sie die[`Stroke`](../shape/stroke/)-Eigenschaft, um auf Stricheigenschaften einer Form zuzugreifen. Sie erstellen keine Instanzen von`Stroke` Klasse direkt.

### Beispiele

Zeigt, wie Stricheigenschaften geändert werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);

// Grundformen wie das Rechteck haben zwei sichtbare Teile.
// 1 - Die Füllung, die für den Bereich innerhalb des Umrisses der Form gilt:
shape.Fill.ForeColor = Color.White;

// 2 - Der Strich, der den Umriss der Form markiert:
// Verschiedene Eigenschaften des Strichs dieser Form ändern.
Stroke stroke = shape.Stroke;
stroke.On = true;
stroke.Weight = 5;
stroke.Color = Color.Red;
stroke.DashStyle = DashStyle.ShortDashDotDot;
stroke.JoinStyle = JoinStyle.Miter;
stroke.EndCap = EndCap.Square;
stroke.LineStyle = ShapeLineStyle.Triple;

doc.Save(ArtifactsDir + "Shape.Stroke.docx");
```

### Siehe auch

* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


