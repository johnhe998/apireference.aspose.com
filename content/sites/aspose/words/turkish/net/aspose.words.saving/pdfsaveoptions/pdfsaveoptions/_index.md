---
title: PdfSaveOptions.PdfSaveOptions
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions inşaatçı. Bir belgeyi the içine kaydetmek için kullanılabilecek bu sınıfın yeni bir örneğini başlatırPdf biçim.
type: docs
weight: 10
url: /tr/net/aspose.words.saving/pdfsaveoptions/pdfsaveoptions/
---
## PdfSaveOptions constructor

Bir belgeyi the içine kaydetmek için kullanılabilecek bu sınıfın yeni bir örneğini başlatırPdf biçim.

```csharp
public PdfSaveOptions()
```

### Örnekler

Bir belgeyi PDF'ye dönüştürürken yazı tiplerini gömerken alt kümelemenin nasıl etkinleştirileceğini veya devre dışı bırakılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Arvo";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Bu belgedeki her iki yazı tipine de erişimimiz olduğundan emin olmak için yazı tipi kaynaklarımızı yapılandırın.
FontSourceBase[] originalFontsSources = FontSettings.DefaultInstance.GetFontsSources();
Aspose.Words.Fonts.FolderFontSource folderFontSource = new Aspose.Words.Fonts.FolderFontSource(FontsDir, true);
FontSettings.DefaultInstance.SetFontsSources(new[] { originalFontsSources[0], folderFontSource });

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(fontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// Belgemiz özel bir yazı tipi içerdiğinden, çıktı belgesine gömmek istenebilir.
// Çıktı PDF'sine her gömülü yazı tipinin her glifini gömmek için "EmbedFullFonts" özelliğini "true" olarak ayarlayın.
// Belgenin boyutu çok büyüyebilir, ancak PDF'yi düzenlersek tüm yazı tiplerini tam olarak kullanabiliriz.
// Fontlara alt küme uygulamak için "EmbedFullFonts" özelliğini "false" olarak ayarlayın, yalnızca glifleri kaydedin
// belgenin kullandığı. Dosya önemli ölçüde daha küçük olacaktır,
// ancak belgeyi düzenlersek herhangi bir özel yazı tipine erişmemiz gerekebilir.
options.EmbedFullFonts = embedFullFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf", options);

if (embedFullFonts)
    Assert.That(500000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));
else
    Assert.That(25000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));

// Orijinal yazı tipi kaynaklarını geri yükleyin.
FontSettings.DefaultInstance.SetFontsSources(originalFontsSources);
```

### Ayrıca bakınız

* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


