---
title: Add
second_title: Référence de l'API Aspose.Slides pour .NET
description: Ajoute un élément mathématique à la fin de la collection.
type: docs
weight: 40
url: /fr/net/aspose.slides.mathtext/imathelementcollection/add/
---
## IMathElementCollection.Add method

Ajoute un élément mathématique à la fin de la collection.

```csharp
public void Add(IMathElement item)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| item | IMathElement | IMathElement à ajouter à la fin de la collection. |

### Exemples

Exemple :

```csharp
[C#]
IMathElementCollection collection = new MathBlock(new MathematicalText("x"));
collection.Add(new MathematicalText("+"));
collection.Add(new MathRadical(new MathematicalText("x"), new MathematicalText("3")));
```

### Voir également

* interface [IMathElement](../../imathelement)
* interface [IMathElementCollection](../../imathelementcollection)
* espace de noms [Aspose.Slides.MathText](../../imathelementcollection)
* Assemblée [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
