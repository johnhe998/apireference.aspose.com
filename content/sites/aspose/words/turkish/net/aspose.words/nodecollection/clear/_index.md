---
title: NodeCollection.Clear
second_title: Aspose.Words for .NET API Referansı
description: NodeCollection yöntem. Bu koleksiyondaki ve belgedeki tüm düğümleri kaldırır.
type: docs
weight: 40
url: /tr/net/aspose.words/nodecollection/clear/
---
## NodeCollection.Clear method

Bu koleksiyondaki ve belgedeki tüm düğümleri kaldırır.

```csharp
public void Clear()
```

### Örnekler

Bir belgeden tüm bölümlerin nasıl kaldırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// Bu belge, tüm belgenin içeriğini içeren ve görüntüleyen birkaç alt düğüme sahip bir bölüme sahiptir.
Assert.AreEqual(1, doc.Sections.Count);
Assert.AreEqual(17, doc.Sections[0].GetChildNodes(NodeType.Any, true).Count);
Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());

// Belgenin tüm alt öğelerini kaldıracak olan bölüm koleksiyonunu temizleyin.
doc.Sections.Clear();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Any, true).Count);
Assert.AreEqual(string.Empty, doc.GetText().Trim());
```

### Ayrıca bakınız

* class [NodeCollection](../)
* ad alanı [Aspose.Words](../../nodecollection/)
* toplantı [Aspose.Words](../../../)


