---
title: Shape.HasSmartArt
second_title: Aspose.Words for .NET API Referansı
description: Shape mülk. Bu Shape bir SmartArt nesnesine sahipse true döndürür.
type: docs
weight: 90
url: /tr/net/aspose.words.drawing/shape/hassmartart/
---
## Shape.HasSmartArt property

Bu Shape bir SmartArt nesnesine sahipse true döndürür.

```csharp
public bool HasSmartArt { get; }
```

### Örnekler

SmartArt nesneleri içeren bir belgedeki şekillerin sayısının nasıl sayılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "SmartArt.docx");

int numberOfSmartArtShapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmartArt);

Assert.AreEqual(2, numberOfSmartArtShapes);
```

### Ayrıca bakınız

* class [Shape](../)
* ad alanı [Aspose.Words.Drawing](../../shape/)
* toplantı [Aspose.Words](../../../)


