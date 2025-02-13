---
title: HorizontalRuleFormat.Height
second_title: Référence de l'API Aspose.Words pour .NET
description: HorizontalRuleFormat propriété. Obtient ou définit la hauteur de la règle horizontale.
type: docs
weight: 30
url: /fr/net/aspose.words.drawing/horizontalruleformat/height/
---
## HorizontalRuleFormat.Height property

Obtient ou définit la hauteur de la règle horizontale.

```csharp
public double Height { get; set; }
```

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentOutOfRangeException | Lance lorsque l'argument est en dehors de la plage de valeurs valides. |

### Remarques

Il s'agit d'un raccourci vers le[`Height`](../../shapebase/height/) propriété.

Les valeurs valides vont de 0 à 1584 inclus.

La valeur par défaut est 1,5.

### Exemples

Montre comment insérer une forme de règle horizontale et personnaliser sa mise en forme.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

Assert.True(shape.IsHorizontalRule);
Assert.True(shape.HorizontalRuleFormat.NoShade);
```

### Voir également

* class [HorizontalRuleFormat](../)
* espace de noms [Aspose.Words.Drawing](../../horizontalruleformat/)
* Assemblée [Aspose.Words](../../../)


