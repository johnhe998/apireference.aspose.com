---
title: Enum PdfFontEmbeddingMode
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.PdfFontEmbeddingMode Sıralama. Aspose.Wordsün fontları nasıl gömmesi gerektiğini belirtir.
type: docs
weight: 5190
url: /tr/net/aspose.words.saving/pdffontembeddingmode/
---
## PdfFontEmbeddingMode enumeration

Aspose.Words'ün fontları nasıl gömmesi gerektiğini belirtir.

```csharp
public enum PdfFontEmbeddingMode
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| EmbedAll | `0` | Aspose.Words tüm yazı tiplerini gömer. |
| EmbedNonstandard | `1` | Aspose.Words, standart Windows yazı tipleri Arial ve Times New Roman hariç tüm yazı tiplerini gömer. MS Word, belgeyi PDF'ye kaydederken yalnızca bu yazı tiplerini gömmediğinden, bu modda yalnızca Arial ve Times New Roman yazı tipleri etkilenir. |
| EmbedNone | `2` | Aspose.Words herhangi bir font yerleştirmez. |

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

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


