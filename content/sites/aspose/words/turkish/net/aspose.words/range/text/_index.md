---
title: Range.Text
second_title: Aspose.Words for .NET API Referansı
description: Range mülk. Aralığın metnini alır.
type: docs
weight: 50
url: /tr/net/aspose.words/range/text/
---
## Range.Text property

Aralığın metnini alır.

```csharp
public string Text { get; }
```

### Notlar

Döndürülen dize, içinde açıklandığı gibi tüm kontrol ve özel karakterleri içerir.[`ControlChar`](../../controlchar/).

### Örnekler

Bir aralığın kapsadığı tüm düğümlerin metin içeriğinin nasıl alınacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");

Assert.AreEqual("Hello world!", doc.Range.Text.Trim());
```

### Ayrıca bakınız

* class [Range](../)
* ad alanı [Aspose.Words](../../range/)
* toplantı [Aspose.Words](../../../)


