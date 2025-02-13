---
title: ShapeBase.CanHaveImage
linktitle: CanHaveImage
articleTitle: CanHaveImage
second_title: Aspose.Words for .NET
description: ShapeBase CanHaveImage property. Returns true if the shape type allows the shape to have an image in C#.
type: docs
weight: 100
url: /net/aspose.words.drawing/shapebase/canhaveimage/
---
## ShapeBase.CanHaveImage property

Returns `true` if the shape type allows the shape to have an image.

```csharp
public bool CanHaveImage { get; }
```

## Remarks

Although Microsoft Word has a special shape type for images, it appears that in Microsoft Word documents any shape except a group shape can have an image, therefore this property returns `true` for all shapes except [`GroupShape`](../../groupshape/).

## Examples

Shows how to insert and rotate an image.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a shape with an image.
Shape shape = builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
Assert.True(shape.CanHaveImage);
Assert.True(shape.HasImage);

// Rotate the image 45 degrees clockwise.
shape.Rotation = 45;

doc.Save(ArtifactsDir + "Shape.Rotate.docx");
```

### See Also

* class [ShapeBase](../)
* namespace [Aspose.Words.Drawing](../../../aspose.words.drawing/)
* assembly [Aspose.Words](../../../)
