---
title: PdfSaveOptions.FontEmbeddingMode
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. Yazı tipi gömme modunu belirtir.
type: docs
weight: 140
url: /tr/net/aspose.words.saving/pdfsaveoptions/fontembeddingmode/
---
## PdfSaveOptions.FontEmbeddingMode property

Yazı tipi gömme modunu belirtir.

```csharp
public PdfFontEmbeddingMode FontEmbeddingMode { get; set; }
```

### Notlar

Varsayılan değerEmbedAll.

Bu ayar yalnızca ANSI (Windows-1252) kodlamasındaki metin için çalışır. Belge, ANSI olmayan metin içeriyorsa, bu ayardan bağımsız olarak ilgili yazı tipleri gömülü olacaktır.

PDF/A ve PDF/UA uyumluluğu, tüm yazı tiplerinin gömülü olmasını gerektirir. EmbedAll değer, PDF/A ve PDF/UA'ya kaydedilirken otomatik olarak kullanılacaktır.

### Örnekler

Aspose.Words'ün Arial ve Times New Roman yazı tiplerini bir PDF belgesine gömmeyi atlayacak şekilde nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "Arial" standart bir yazı tipidir ve "Courier New" standart olmayan bir yazı tipidir.
builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// Çıktı PDF'sine her gömülü yazı tipinin her glifini gömmek için "EmbedFullFonts" özelliğini "true" olarak ayarlayın.
options.EmbedFullFonts = true;

// Tüm yazı tiplerini çıktı PDF'sine gömmek için "FontEmbeddingMode" özelliğini "EmbedAll" olarak ayarlayın.
// Çıktı PDF'sine yalnızca standart olmayan yazı tiplerinin yerleştirilmesine izin vermek için "FontEmbeddingMode" özelliğini "EmbedNonstandard" olarak ayarlayın.
// Çıktı PDF'sine herhangi bir yazı tipi gömmemek için "FontEmbeddingMode" özelliğini "EmbedNone" olarak ayarlayın.
options.FontEmbeddingMode = pdfFontEmbeddingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf", options);

switch (pdfFontEmbeddingMode)
{
    case PdfFontEmbeddingMode.EmbedAll:
        Assert.That(1000000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNonstandard:
        Assert.That(480000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNone:
        Assert.That(4217, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
}
```

### Ayrıca bakınız

* enum [PdfFontEmbeddingMode](../../pdffontembeddingmode/)
* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


