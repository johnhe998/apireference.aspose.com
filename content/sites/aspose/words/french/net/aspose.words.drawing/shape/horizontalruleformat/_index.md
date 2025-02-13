---
title: Shape.HorizontalRuleFormat
second_title: Référence de l'API Aspose.Words pour .NET
description: Shape propriété. Permet daccéder aux propriétés de la forme du filet horizontal. Pour une forme qui nest pas un filet horizontal renvoie null.
type: docs
weight: 100
url: /fr/net/aspose.words.drawing/shape/horizontalruleformat/
---
## Shape.HorizontalRuleFormat property

Permet d'accéder aux propriétés de la forme du filet horizontal. Pour une forme qui n'est pas un filet horizontal, renvoie null.

```csharp
public HorizontalRuleFormat HorizontalRuleFormat { get; }
```

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

* class [HorizontalRuleFormat](../../horizontalruleformat/)
* class [Shape](../)
* espace de noms [Aspose.Words.Drawing](../../shape/)
* Assemblée [Aspose.Words](../../../)


