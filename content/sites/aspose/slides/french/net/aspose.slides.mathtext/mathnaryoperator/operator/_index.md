---
title: Operator
second_title: Référence de l'API Aspose.Slides pour .NET
description: Caractère dopérateur Naire Par exemple   
type: docs
weight: 70
url: /fr/net/aspose.slides.mathtext/mathnaryoperator/operator/
---
## MathNaryOperator.Operator property

Caractère d'opérateur Naire Par exemple : '∑', '∫'

```csharp
public char Operator { get; set; }
```

### Exemples

Exemple :

```csharp
[C#]
IMathNaryOperator naryOperator = new MathematicalText("x").Nary(MathNaryOperatorTypes.Summation, "x=1", "100");
char operatorSymbol = naryOperator.Operator;
```

### Voir également

* class [MathNaryOperator](../../mathnaryoperator)
* espace de noms [Aspose.Slides.MathText](../../mathnaryoperator)
* Assemblée [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
