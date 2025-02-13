---
title: Shape.HasSmartArt
second_title: Référence de l'API Aspose.Words pour .NET
description: Shape propriété. Renvoie vrai si cette forme a un objet SmartArt.
type: docs
weight: 90
url: /fr/net/aspose.words.drawing/shape/hassmartart/
---
## Shape.HasSmartArt property

Renvoie vrai si cette forme a un objet SmartArt.

```csharp
public bool HasSmartArt { get; }
```

### Exemples

Montre comment compter le nombre de formes dans un document avec des objets SmartArt.

```csharp
Document doc = new Document(MyDir + "SmartArt.docx");

int numberOfSmartArtShapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmartArt);

Assert.AreEqual(2, numberOfSmartArtShapes);
```

### Voir également

* class [Shape](../)
* espace de noms [Aspose.Words.Drawing](../../shape/)
* Assemblée [Aspose.Words](../../../)


