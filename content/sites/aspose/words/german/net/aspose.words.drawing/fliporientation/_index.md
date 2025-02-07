---
title: Enum FlipOrientation
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.FlipOrientation opsomming. Mögliche Werte für die Orientierung einer Form.
type: docs
weight: 840
url: /de/net/aspose.words.drawing/fliporientation/
---
## FlipOrientation enumeration

Mögliche Werte für die Orientierung einer Form.

```csharp
[Flags]
public enum FlipOrientation
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Koordinaten werden nicht gespiegelt. |
| Horizontal | `1` | Spiegeln Sie entlang der y-Achse und kehren Sie die x-Koordinaten um. |
| Vertical | `2` | Spiegeln Sie entlang der x-Achse und kehren Sie die y-Koordinaten um. |
| Both | `3` | Spiegeln Sie entlang der y- und x-Achse. |

### Beispiele

Zeigt, wie eine Form auf einer Achse gespiegelt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügt eine Bildform ein und belässt ihre Ausrichtung im Standardzustand.
Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

Assert.AreEqual(FlipOrientation.None, shape.FlipOrientation);

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 250,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Setzen Sie die Eigenschaft "FlipOrientation" auf "FlipOrientation.Horizontal", um die zweite Form auf der y-Achse zu spiegeln,
// daraus ein horizontales Spiegelbild der ersten Form machen.
shape.FlipOrientation = FlipOrientation.Horizontal;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 250, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Setzen Sie die Eigenschaft "FlipOrientation" auf "FlipOrientation.Horizontal", um die dritte Form auf der x-Achse zu spiegeln,
// daraus ein vertikales Spiegelbild der ersten Form machen.
shape.FlipOrientation = FlipOrientation.Vertical;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 250,
    RelativeVerticalPosition.TopMargin, 250, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Setzen Sie die Eigenschaft "FlipOrientation" auf "FlipOrientation.Horizontal", um die vierte Form sowohl auf der x- als auch auf der y-Achse zu spiegeln,
// daraus ein horizontales und vertikales Spiegelbild der ersten Form machen.
shape.FlipOrientation = FlipOrientation.Both;

doc.Save(ArtifactsDir + "Shape.FlipShapeOrientation.docx");
```

### Siehe auch

* property [FlipOrientation](../shapebase/fliporientation/)
* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


