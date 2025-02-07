---
title: MarkdownSaveOptions.ExportImagesAsBase64
second_title: Aspose.Words for .NET API Referansı
description: MarkdownSaveOptions mülk. Görüntülerin çıktı dosyasına Base64 biçiminde kaydedilip kaydedilmeyeceğini belirtir. Varsayılanyanlış .
type: docs
weight: 20
url: /tr/net/aspose.words.saving/markdownsaveoptions/exportimagesasbase64/
---
## MarkdownSaveOptions.ExportImagesAsBase64 property

Görüntülerin çıktı dosyasına Base64 biçiminde kaydedilip kaydedilmeyeceğini belirtir. Varsayılan`yanlış` .

```csharp
public bool ExportImagesAsBase64 { get; set; }
```

### Notlar

Bu özellik olarak ayarlandığında`doğru`görüntü verileri doğrudan dışa aktarılır  **resim** öğeler ve ayrı dosyalar oluşturulmaz.

### Örnekler

İçinde gömülü resimler bulunan bir .md belgesinin nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Images.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ExportImagesAsBase64 = exportImagesAsBase64 };

doc.Save(ArtifactsDir + "MarkdownSaveOptions.ExportImagesAsBase64.md", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "MarkdownSaveOptions.ExportImagesAsBase64.md");

Assert.True(exportImagesAsBase64
    ? outDocContents.Contains("data:image/jpeg;base64")
    : outDocContents.Contains("MarkdownSaveOptions.ExportImagesAsBase64.001.jpeg"));
```

### Ayrıca bakınız

* class [MarkdownSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../markdownsaveoptions/)
* toplantı [Aspose.Words](../../../)


