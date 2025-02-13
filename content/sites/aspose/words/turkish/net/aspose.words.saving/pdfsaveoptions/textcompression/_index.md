---
title: PdfSaveOptions.TextCompression
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. Belgedeki tüm metin içeriği için kullanılacak sıkıştırma türünü belirtir.
type: docs
weight: 260
url: /tr/net/aspose.words.saving/pdfsaveoptions/textcompression/
---
## PdfSaveOptions.TextCompression property

Belgedeki tüm metin içeriği için kullanılacak sıkıştırma türünü belirtir.

```csharp
public PdfTextCompression TextCompression { get; set; }
```

### Notlar

VarsayılanFlate.

Bir belgeyi sıkıştırma olmadan kaydederken çıktı boyutunu önemli ölçüde artırır.

### Örnekler

Bir belgeyi PDF'ye kaydederken metin sıkıştırmanın nasıl uygulanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

for (int i = 0; i < 100; i++)
    builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                    "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// "TextCompression" özelliğini "PdfTextCompression.None" olarak ayarlayın
// belgeyi PDF'ye kaydettiğimizde metne sıkıştırma.
// ZIP sıkıştırmasını uygulamak için "TextCompression" özelliğini "PdfTextCompression.Flate" olarak ayarlayın
// belgeyi PDF'ye kaydettiğimizde metne. Belge ne kadar büyük olursa, bunun yaratacağı etki de o kadar büyük olur.
options.TextCompression = pdfTextCompression;

doc.Save(ArtifactsDir + "PdfSaveOptions.TextCompression.pdf", options);
```

### Ayrıca bakınız

* enum [PdfTextCompression](../../pdftextcompression/)
* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


