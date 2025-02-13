---
title: DocumentBuilder.InsertHorizontalRule
second_title: Référence de l'API Aspose.Words pour .NET
description: DocumentBuilder méthode. Insère une forme de règle horizontale dans le document.
type: docs
weight: 320
url: /fr/net/aspose.words/documentbuilder/inserthorizontalrule/
---
## DocumentBuilder.InsertHorizontalRule method

Insère une forme de règle horizontale dans le document.

```csharp
public Shape InsertHorizontalRule()
```

### Return_Value

La forme qui est une règle horizontale.

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

* class [Shape](../../../aspose.words.drawing/shape/)
* class [DocumentBuilder](../)
* espace de noms [Aspose.Words](../../documentbuilder/)
* Assemblée [Aspose.Words](../../../)


