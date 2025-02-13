---
title: ShapeBase.CanHaveImage
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Renvoie vrai si le type de forme permet à la forme davoir une image.
type: docs
weight: 100
url: /fr/net/aspose.words.drawing/shapebase/canhaveimage/
---
## ShapeBase.CanHaveImage property

Renvoie vrai si le type de forme permet à la forme d'avoir une image.

```csharp
public bool CanHaveImage { get; }
```

### Remarques

Bien que Microsoft Word ait un type de forme spécial pour les images, il semble que dans les documents Microsoft Word, toute forme à l'exception d'une forme de groupe peut avoir une image, par conséquent cette propriété renvoie true pour toutes les formes sauf[`GroupShape`](../../groupshape/).

### Exemples

Montre comment insérer et faire pivoter une image.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère une forme avec une image.
Shape shape = builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
Assert.True(shape.CanHaveImage);
Assert.True(shape.HasImage);

// Faites pivoter l'image de 45 degrés dans le sens des aiguilles d'une montre.
shape.Rotation = 45;

doc.Save(ArtifactsDir + "Shape.Rotate.docx");
```

### Voir également

* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


