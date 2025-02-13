---
title: ShapeBase.BehindText
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Spécifie si la forme est audessous ou audessus du texte.
type: docs
weight: 50
url: /fr/net/aspose.words.drawing/shapebase/behindtext/
---
## ShapeBase.BehindText property

Spécifie si la forme est au-dessous ou au-dessus du texte.

```csharp
public bool BehindText { get; set; }
```

### Remarques

N'a d'effet que pour les formes de niveau supérieur.

La valeur par défaut est **faux**.

### Exemples

Montre comment insérer une image flottante au centre d'une page.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère une image flottante qui apparaîtra derrière le texte superposé et l'aligne au centre de la page.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Voir également

* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


