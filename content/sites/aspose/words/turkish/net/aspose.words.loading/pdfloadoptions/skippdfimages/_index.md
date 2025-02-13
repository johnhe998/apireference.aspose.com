---
title: PdfLoadOptions.SkipPdfImages
second_title: Aspose.Words for .NET API Referansı
description: PdfLoadOptions mülk. PDF belgesi yüklenirken görüntülerin atlanması gerekip gerekmediğini belirten bayrağı alır veya ayarlar. Varsayılan Yanlıştır.
type: docs
weight: 40
url: /tr/net/aspose.words.loading/pdfloadoptions/skippdfimages/
---
## PdfLoadOptions.SkipPdfImages property

PDF belgesi yüklenirken görüntülerin atlanması gerekip gerekmediğini belirten bayrağı alır veya ayarlar. Varsayılan, Yanlış'tır.

```csharp
public bool SkipPdfImages { get; set; }
```

### Örnekler

PDF dosyaları yüklenirken görüntülerin nasıl atlanacağını gösterir.

```csharp
PdfLoadOptions options = new PdfLoadOptions();
options.SkipPdfImages = isSkipPdfImages;

Document doc = new Document(MyDir + "Images.pdf", options);
NodeCollection shapeCollection = doc.GetChildNodes(NodeType.Shape, true);

if (isSkipPdfImages)
{
    Assert.AreEqual(shapeCollection.Count, 0);
}
else
{
    Assert.AreNotEqual(shapeCollection.Count, 0);
}
```

### Ayrıca bakınız

* class [PdfLoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../pdfloadoptions/)
* toplantı [Aspose.Words](../../../)


