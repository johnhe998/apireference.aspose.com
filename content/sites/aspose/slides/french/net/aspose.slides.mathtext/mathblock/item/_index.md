---
title: Item
second_title: Référence de l'API Aspose.Slides pour .NET
description: Obtient ou définit IMathElement à lindex spécifié.
type: docs
weight: 40
url: /fr/net/aspose.slides.mathtext/mathblock/item/
---
## MathBlock indexer

Obtient ou définit IMathElement à l'index spécifié.

```csharp
public IMathElement this[int index] { get; set; }
```

| Paramètre | La description |
| --- | --- |
| index | L'index de base zéro de l'élément |

### Return_Value

L'élément mathématique.

### Exemples

Exemple :

```csharp
[C#]
MathBlock mathBlock = new MathBlock(new MathematicalText("x"));
IMathElement firstElem = mathBlock[0];
```

### Voir également

* interface [IMathElement](../../imathelement)
* class [MathBlock](../../mathblock)
* espace de noms [Aspose.Slides.MathText](../../mathblock)
* Assemblée [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
