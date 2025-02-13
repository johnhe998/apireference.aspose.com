---
title: ShapeBase.Rotation
second_title: Aspose.Words för .NET API Referens
description: ShapeBase fast egendom. Definierar vinkeln i grader som en form roteras. Positivt värde motsvarar medurs rotationsvinkel.
type: docs
weight: 430
url: /sv/net/aspose.words.drawing/shapebase/rotation/
---
## ShapeBase.Rotation property

Definierar vinkeln (i grader) som en form roteras. Positivt värde motsvarar medurs rotationsvinkel.

```csharp
public double Rotation { get; set; }
```

### Anmärkningar

Standardvärdet är 0.

### Exempel

Visar hur man infogar och roterar en bild.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en form med en bild.
Shape shape = builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
Assert.True(shape.CanHaveImage);
Assert.True(shape.HasImage);

// Rotera bilden 45 grader medurs.
shape.Rotation = 45;

doc.Save(ArtifactsDir + "Shape.Rotate.docx");
```

### Se även

* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


