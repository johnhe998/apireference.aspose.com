---
title: Node.Clone
second_title: Aspose.Words for .NET API Referansı
description: Node yöntem. Düğümün bir kopyasını oluşturur.
type: docs
weight: 100
url: /tr/net/aspose.words/node/clone/
---
## Node.Clone method

Düğümün bir kopyasını oluşturur.

```csharp
public Node Clone(bool isCloneChildren)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| isCloneChildren | Boolean | Belirtilen düğüm altındaki alt ağacı yinelemeli olarak klonlamak için doğru; false yalnızca düğümün kendisini klonlamak için. |

### Geri dönüş değeri

Klonlanmış düğüm.

### Notlar

Bu yöntem, düğümler için bir kopya oluşturucu görevi görür. Klonlanan düğümün üst öğesi yoktur, ancak orijinal düğümle aynı belgeye aittir.

Bu yöntem her zaman düğümün derin bir kopyasını gerçekleştirir. buisCloneChildren parametre , tüm alt düğümlerin de kopyalanıp kopyalanmayacağını belirtir.

### Örnekler

Bileşik bir düğümün nasıl klonlanacağını gösterir.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;
para.AppendChild(new Run(doc, "Hello world!"));

// Aşağıda bir bileşik düğümü klonlamanın iki yolu bulunmaktadır.
// 1 - Bir düğümün klonunu oluşturun ve ayrıca alt düğümlerinin her birinin bir klonunu oluşturun.
Node cloneWithChildren = para.Clone(true);

Assert.IsTrue(((CompositeNode)cloneWithChildren).HasChildNodes);
Assert.AreEqual("Hello world!", cloneWithChildren.GetText().Trim());

// 2 - Herhangi bir çocuk olmadan kendi başına bir düğümün klonunu oluşturun.
Node cloneWithoutChildren = para.Clone(false);

Assert.IsFalse(((CompositeNode)cloneWithoutChildren).HasChildNodes);
Assert.AreEqual(string.Empty, cloneWithoutChildren.GetText().Trim());
```

### Ayrıca bakınız

* class [Node](../)
* ad alanı [Aspose.Words](../../node/)
* toplantı [Aspose.Words](../../../)


