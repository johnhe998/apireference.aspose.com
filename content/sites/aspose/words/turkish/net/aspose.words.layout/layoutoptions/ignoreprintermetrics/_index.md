---
title: LayoutOptions.IgnorePrinterMetrics
second_title: Aspose.Words for .NET API Referansı
description: LayoutOptions mülk. Belgeyi düzenlemek için yazıcı metriklerini kullan uyumluluk seçeneğinin yoksayılıp yok sayılmadığının göstergesini alır veya ayarlar. Varsayılan Değer Doğrudur.
type: docs
weight: 50
url: /tr/net/aspose.words.layout/layoutoptions/ignoreprintermetrics/
---
## LayoutOptions.IgnorePrinterMetrics property

"Belgeyi düzenlemek için yazıcı metriklerini kullan" uyumluluk seçeneğinin yoksayılıp yok sayılmadığının göstergesini alır veya ayarlar. Varsayılan Değer Doğru'dur.

```csharp
public bool IgnorePrinterMetrics { get; set; }
```

### Örnekler

'Belgeyi düzenlemek için yazıcı ölçümlerini kullan' seçeneğinin nasıl göz ardı edileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

doc.LayoutOptions.IgnorePrinterMetrics = false;

doc.Save(ArtifactsDir + "Document.IgnorePrinterMetrics.docx");
```

### Ayrıca bakınız

* class [LayoutOptions](../)
* ad alanı [Aspose.Words.Layout](../../layoutoptions/)
* toplantı [Aspose.Words](../../../)


