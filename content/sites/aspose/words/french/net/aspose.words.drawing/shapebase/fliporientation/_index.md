---
title: ShapeBase.FlipOrientation
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Change lorientation dune forme.
type: docs
weight: 180
url: /fr/net/aspose.words.drawing/shapebase/fliporientation/
---
## ShapeBase.FlipOrientation property

Change l'orientation d'une forme.

```csharp
public FlipOrientation FlipOrientation { get; set; }
```

### Remarques

La valeur par défaut estNone.

### Exemples

Montre comment retourner une forme sur un axe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère une forme d'image et laisse son orientation dans son état par défaut.
Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

Assert.AreEqual(FlipOrientation.None, shape.FlipOrientation);

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 250,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Définissez la propriété "FlipOrientation" sur "FlipOrientation.Horizontal" pour retourner la deuxième forme sur l'axe des ordonnées,
// en faisant une image miroir horizontale de la première forme.
shape.FlipOrientation = FlipOrientation.Horizontal;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 250, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Définissez la propriété "FlipOrientation" sur "FlipOrientation.Horizontal" pour retourner la troisième forme sur l'axe des x,
// en faisant une image miroir verticale de la première forme.
shape.FlipOrientation = FlipOrientation.Vertical;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 250,
    RelativeVerticalPosition.TopMargin, 250, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Définissez la propriété "FlipOrientation" sur "FlipOrientation.Horizontal" pour retourner la quatrième forme sur les axes x et y,
// en faisant une image miroir horizontale et verticale de la première forme.
shape.FlipOrientation = FlipOrientation.Both;

doc.Save(ArtifactsDir + "Shape.FlipShapeOrientation.docx");
```

### Voir également

* enum [FlipOrientation](../../fliporientation/)
* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


