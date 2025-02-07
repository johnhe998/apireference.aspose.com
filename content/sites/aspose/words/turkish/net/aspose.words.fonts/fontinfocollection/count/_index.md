---
title: FontInfoCollection.Count
second_title: Aspose.Words for .NET API Referansı
description: FontInfoCollection mülk. Koleksiyonda bulunan öğelerin sayısını alır.
type: docs
weight: 10
url: /tr/net/aspose.words.fonts/fontinfocollection/count/
---
## FontInfoCollection.Count property

Koleksiyonda bulunan öğelerin sayısını alır.

```csharp
public int Count { get; }
```

### Örnekler

Boş belgede bulunan yazı tipleriyle ilgili bilgileri gösterir.

```csharp
Document doc = new Document();

// Boş bir belge 3 varsayılan yazı tipi içerir. Belgedeki her yazı tipi
// bu yazı tipiyle ilgili ayrıntıları içeren karşılık gelen bir FontInfo nesnesine sahip olacaktır.
Assert.AreEqual(3, doc.FontInfos.Count);

Assert.True(doc.FontInfos.Contains("Times New Roman"));
Assert.AreEqual(204, doc.FontInfos["Times New Roman"].Charset);

Assert.True(doc.FontInfos.Contains("Symbol"));
Assert.True(doc.FontInfos.Contains("Arial"));
```

### Ayrıca bakınız

* class [FontInfoCollection](../)
* ad alanı [Aspose.Words.Fonts](../../fontinfocollection/)
* toplantı [Aspose.Words](../../../)


