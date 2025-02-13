---
title: ShapeBase.AspectRatioLocked
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Spécifie si les proportions de la forme sont verrouillées.
type: docs
weight: 40
url: /fr/net/aspose.words.drawing/shapebase/aspectratiolocked/
---
## ShapeBase.AspectRatioLocked property

Spécifie si les proportions de la forme sont verrouillées.

```csharp
public bool AspectRatioLocked { get; set; }
```

### Remarques

La valeur par défaut dépend de la[`ShapeType`](../shapetype/) , pour le ShapeType.Image c'est **vrai** mais pour les autres types de forme c'est **faux**.

N'a d'effet que sur les formes de niveau supérieur.

### Exemples

Montre comment verrouiller/déverrouiller le rapport d'aspect d'une forme.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère une forme. Si nous ouvrons ce document dans Microsoft Word, nous pouvons faire un clic gauche sur la forme pour révéler
// huit poignées de redimensionnement autour de son périmètre, sur lesquelles nous pouvons cliquer et faire glisser pour modifier sa taille.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

// Définissez la propriété "AspectRatioLocked" sur "true" pour conserver le rapport d'aspect de la forme
// lors de l'utilisation de l'une des quatre poignées de redimensionnement en diagonale, qui modifient à la fois la hauteur et la largeur de l'image.
// L'utilisation de poignées de redimensionnement orthogonales qui modifient la hauteur ou la largeur modifiera toujours le rapport d'aspect.
// Définissez la propriété "AspectRatioLocked" sur "false" pour nous permettre de
// changez librement le rapport d'aspect de l'image avec toutes les poignées de redimensionnement.
shape.AspectRatioLocked = lockAspectRatio;

doc.Save(ArtifactsDir + "Shape.AspectRatio.docx");
```

### Voir également

* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


