---
title: Stroke.JoinStyle
second_title: Aspose.Words für .NET-API-Referenz
description: Stroke eigendom. Definiert den Verbindungsstil einer Polylinie.
type: docs
weight: 110
url: /de/net/aspose.words.drawing/stroke/joinstyle/
---
## Stroke.JoinStyle property

Definiert den Verbindungsstil einer Polylinie.

```csharp
public JoinStyle JoinStyle { get; set; }
```

### Bemerkungen

Der Standardwert istRound.

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

* enum [JoinStyle](../../joinstyle/)
* class [Stroke](../)
* namensraum [Aspose.Words.Drawing](../../stroke/)
* Montage [Aspose.Words](../../../)


