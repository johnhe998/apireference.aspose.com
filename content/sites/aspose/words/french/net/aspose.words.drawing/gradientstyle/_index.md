---
title: Enum GradientStyle
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Drawing.GradientStyle énumération. Spécifie le style dun remplissage dégradé.
type: docs
weight: 870
url: /fr/net/aspose.words.drawing/gradientstyle/
---
## GradientStyle enumeration

Spécifie le style d'un remplissage dégradé.

```csharp
public enum GradientStyle
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| None | `-1` | Pas de dégradé. |
| Horizontal | `1` | Dégradé s'étendant horizontalement sur un objet. |
| Vertical | `2` | Dégradé descendant verticalement vers le bas d'un objet. |
| DiagonalUp | `3` | Dégradé diagonal allant d'un coin inférieur jusqu'au coin opposé. |
| DiagonalDown | `4` | Dégradé diagonal allant d'un coin supérieur vers le coin opposé. |
| FromCorner | `5` | Dégradé allant d'un coin aux trois autres coins. |
| FromCenter | `6` | Dégradé allant du centre vers les coins. |

### Exemples

Montre comment remplir une forme avec des dégradés.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// Appliquez un remplissage dégradé à une couleur à la forme avec ForeColor de remplissage dégradé.
shape.Fill.OneColorGradient(Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2, 0.1);

Assert.AreEqual(Color.Red.ToArgb(), shape.Fill.ForeColor.ToArgb());
Assert.AreEqual(GradientStyle.Horizontal, shape.Fill.GradientStyle);
Assert.AreEqual(GradientVariant.Variant2, shape.Fill.GradientVariant);
Assert.AreEqual(270, shape.Fill.GradientAngle);

shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// Appliquez un remplissage dégradé bicolore à la forme.
shape.Fill.TwoColorGradient(GradientStyle.FromCorner, GradientVariant.Variant4);
// Change la couleur de fond du remplissage dégradé.
shape.Fill.BackColor = Color.Yellow;
// Notez que change "GradientAngle" pour "GradientStyle.FromCorner/GradientStyle.FromCenter"
// le remplissage dégradé n'a aucun effet, cela ne fonctionnera que pour le dégradé linéaire.
shape.Fill.GradientAngle = 15;

Assert.AreEqual(Color.Yellow.ToArgb(), shape.Fill.BackColor.ToArgb());
Assert.AreEqual(GradientStyle.FromCorner, shape.Fill.GradientStyle);
Assert.AreEqual(GradientVariant.Variant4, shape.Fill.GradientVariant);
Assert.AreEqual(0, shape.Fill.GradientAngle);

// Utilisez l'option de conformité pour définir la forme à l'aide de DML si vous souhaitez obtenir "GradientStyle",
// Propriétés "GradientVariant" et "GradientAngle" après l'enregistrement du document.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientFill.docx", saveOptions);
```

### Voir également

* espace de noms [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Assemblée [Aspose.Words](../../)


