---
title: HorizontalRuleFormat.Alignment
second_title: Référence de l'API Aspose.Words pour .NET
description: HorizontalRuleFormat propriété. Obtient ou définit lalignement de la règle horizontale.
type: docs
weight: 10
url: /fr/net/aspose.words.drawing/horizontalruleformat/alignment/
---
## HorizontalRuleFormat.Alignment property

Obtient ou définit l'alignement de la règle horizontale.

```csharp
public HorizontalRuleAlignment Alignment { get; set; }
```

### Remarques

La valeur par défaut estLeft.

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

* enum [HorizontalRuleAlignment](../../horizontalrulealignment/)
* class [HorizontalRuleFormat](../)
* espace de noms [Aspose.Words.Drawing](../../horizontalruleformat/)
* Assemblée [Aspose.Words](../../../)


