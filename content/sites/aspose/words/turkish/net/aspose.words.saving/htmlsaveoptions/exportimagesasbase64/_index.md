---
title: HtmlSaveOptions.ExportImagesAsBase64
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Görüntülerin HTML MHTML veya EPUB çıktısına Base64 biçiminde kaydedilip kaydedilmeyeceğini belirtir. Varsayılanyanlış .
type: docs
weight: 180
url: /tr/net/aspose.words.saving/htmlsaveoptions/exportimagesasbase64/
---
## HtmlSaveOptions.ExportImagesAsBase64 property

Görüntülerin HTML, MHTML veya EPUB çıktısına Base64 biçiminde kaydedilip kaydedilmeyeceğini belirtir. Varsayılan`yanlış` .

```csharp
public bool ExportImagesAsBase64 { get; set; }
```

### Notlar

Bu özellik olarak ayarlandığında`doğru`görüntü verileri doğrudan dışa aktarılır  **resim** öğeler ve ayrı dosyalar oluşturulmaz.

### Örnekler

Kaydedilmiş bir HTML belgesinin içine yazı tiplerinin nasıl gömüleceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportFontsAsBase64 = true,
    CssStyleSheetType = CssStyleSheetType.Embedded,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportFontsAsBase64.html", options);
```

İçinde gömülü resimler bulunan bir .html belgesinin nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportImagesAsBase64 = exportImagesAsBase64,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportImagesAsBase64.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportImagesAsBase64.html");

Assert.True(exportImagesAsBase64
    ? outDocContents.Contains("<img src=\"data:image/png;base64")
    : outDocContents.Contains("<img src=\"HtmlSaveOptions.ExportImagesAsBase64.001.png\""));
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


