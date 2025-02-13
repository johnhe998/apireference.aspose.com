---
title: ShapeBase.DistanceRight
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Renvoie ou définit la distance en points entre le texte du document et le bord droit de la forme.
type: docs
weight: 150
url: /fr/net/aspose.words.drawing/shapebase/distanceright/
---
## ShapeBase.DistanceRight property

Renvoie ou définit la distance (en points) entre le texte du document et le bord droit de la forme.

```csharp
public double DistanceRight { get; set; }
```

### Remarques

La valeur par défaut est 1/8 de pouce.

N'a d'effet que pour les formes de niveau supérieur.

### Exemples

Montre comment définir la distance d'habillage d'un texte entourant une forme.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère un rectangle et fait en sorte que le texte s'enroule étroitement autour de ses limites.
Shape shape = builder.InsertShape(ShapeType.Rectangle, 150, 150);
shape.WrapType = WrapType.Tight;

// Définit la distance minimale entre la forme et le texte environnant à 40 pt de tous les côtés.
shape.DistanceTop = 40;
shape.DistanceBottom = 40;
shape.DistanceLeft = 40;
shape.DistanceRight = 40;

// Rapprochez la forme du centre de la page, puis faites pivoter la forme de 60 degrés dans le sens des aiguilles d'une montre.
shape.Top = 75;
shape.Left = 150; 
shape.Rotation = 60;

// Ajoute du texte qui s'enroulera autour de la forme.
builder.Font.Size = 24;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
              "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

doc.Save(ArtifactsDir + "Shape.Coordinates.docx");
```

### Voir également

* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


