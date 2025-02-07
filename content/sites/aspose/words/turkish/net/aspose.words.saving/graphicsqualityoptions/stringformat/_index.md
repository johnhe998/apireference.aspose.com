---
title: GraphicsQualityOptions.StringFormat
second_title: Aspose.Words for .NET API Referansı
description: GraphicsQualityOptions mülk. Metin düzeni bilgilerini alır veya ayarlar hizalama yönlendirme ve sekme durakları gibi görüntüleme manipülasyonları üç nokta ekleme ve ulusal rakam değiştirme gibi ve OpenType özellikleri.
type: docs
weight: 60
url: /tr/net/aspose.words.saving/graphicsqualityoptions/stringformat/
---
## GraphicsQualityOptions.StringFormat property

Metin düzeni bilgilerini alır veya ayarlar (hizalama, yönlendirme ve sekme durakları gibi) görüntüleme manipülasyonları (üç nokta ekleme ve ulusal rakam değiştirme gibi) ve OpenType özellikleri.

```csharp
public StringFormat StringFormat { get; set; }
```

### Örnekler

Belgeleri görüntü biçimlerine dönüştürürken işleme kalitesi seçeneklerinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

GraphicsQualityOptions qualityOptions = new GraphicsQualityOptions
{
    SmoothingMode = SmoothingMode.AntiAlias,
    TextRenderingHint = TextRenderingHint.ClearTypeGridFit,
    CompositingMode = CompositingMode.SourceOver,
    CompositingQuality = CompositingQuality.HighQuality,
    InterpolationMode = InterpolationMode.High,
    StringFormat = StringFormat.GenericTypographic
};

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg);
saveOptions.GraphicsQualityOptions = qualityOptions;

doc.Save(ArtifactsDir + "ImageSaveOptions.GraphicsQuality.jpg", saveOptions);
```

### Ayrıca bakınız

* class [GraphicsQualityOptions](../)
* ad alanı [Aspose.Words.Saving](../../graphicsqualityoptions/)
* toplantı [Aspose.Words](../../../)


