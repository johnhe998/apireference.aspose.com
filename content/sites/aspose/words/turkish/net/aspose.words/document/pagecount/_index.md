---
title: Document.PageCount
second_title: Aspose.Words for .NET API Referansı
description: Document mülk. En son sayfa düzeni işlemi tarafından hesaplandığı şekliyle belgedeki sayfa sayısını alır.
type: docs
weight: 300
url: /tr/net/aspose.words/document/pagecount/
---
## Document.PageCount property

En son sayfa düzeni işlemi tarafından hesaplandığı şekliyle belgedeki sayfa sayısını alır.

```csharp
public int PageCount { get; }
```

### Örnekler

Belgedeki sayfa sayısının nasıl sayılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Page 2");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Page 3");

// Belgenin beklenen sayfa sayısını doğrulayın.
Assert.AreEqual(3, doc.PageCount);

// PageCount özelliğinin alınması, değeri hesaplamak için belgenin sayfa düzenini çağırdı.
// Belgeyi sabit bir sayfa kaydetme biçimine dönüştürürken bu işlemin yeniden yapılması gerekmeyecek,
// .pdf gibi. Böylece, özellikle daha karmaşık belgelerde biraz zaman kazanabilirsiniz.
doc.Save(ArtifactsDir + "Document.GetPageCount.pdf");
```

### Ayrıca bakınız

* method [UpdatePageLayout](../updatepagelayout/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


