---
title: HtmlSaveOptions.ExportFontsAsBase64
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Yazı tipi kaynaklarının Base64 kodlamasında HTMLye gömülmesi gerekip gerekmediğini belirtir. Varsayılanyanlış .
type: docs
weight: 160
url: /tr/net/aspose.words.saving/htmlsaveoptions/exportfontsasbase64/
---
## HtmlSaveOptions.ExportFontsAsBase64 property

Yazı tipi kaynaklarının Base64 kodlamasında HTML'ye gömülmesi gerekip gerekmediğini belirtir. Varsayılan`yanlış` .

```csharp
public bool ExportFontsAsBase64 { get; set; }
```

### Notlar

Varsayılan olarak, yazı tipleri ayrı dosyalara yazılır. Bu seçenek olarak ayarlanırsa`doğru`, yazı tipleri, Base64 kodlamasında belgenin CSS'sine gömülü olacaktır.

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


