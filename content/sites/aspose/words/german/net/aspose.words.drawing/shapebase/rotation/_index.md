---
title: ShapeBase.Rotation
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Definiert den Winkel in Grad um den eine Form gedreht wird. Ein positiver Wert entspricht einem Drehwinkel im Uhrzeigersinn.
type: docs
weight: 430
url: /de/net/aspose.words.drawing/shapebase/rotation/
---
## ShapeBase.Rotation property

Definiert den Winkel (in Grad), um den eine Form gedreht wird. Ein positiver Wert entspricht einem Drehwinkel im Uhrzeigersinn.

```csharp
public double Rotation { get; set; }
```

### Bemerkungen

Der Standardwert ist 0.

### Beispiele

Zeigt, wie ein Bild eingefügt und gedreht wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Eine Form mit einem Bild einfügen.
Shape shape = builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
Assert.True(shape.CanHaveImage);
Assert.True(shape.HasImage);

// Drehe das Bild um 45 Grad im Uhrzeigersinn.
shape.Rotation = 45;

doc.Save(ArtifactsDir + "Shape.Rotate.docx");
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


