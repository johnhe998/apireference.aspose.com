---
title: ShapeBase.Rotation
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Définit langle en degrés de rotation dune forme. Une valeur positive correspond à un angle de rotation dans le sens des aiguilles dune montre.
type: docs
weight: 430
url: /fr/net/aspose.words.drawing/shapebase/rotation/
---
## ShapeBase.Rotation property

Définit l'angle (en degrés) de rotation d'une forme. Une valeur positive correspond à un angle de rotation dans le sens des aiguilles d'une montre.

```csharp
public double Rotation { get; set; }
```

### Remarques

La valeur par défaut est 0.

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


