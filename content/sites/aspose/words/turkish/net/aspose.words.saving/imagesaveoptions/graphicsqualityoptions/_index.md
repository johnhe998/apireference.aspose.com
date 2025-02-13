---
title: ImageSaveOptions.GraphicsQualityOptions
second_title: Aspose.Words for .NET API Referansı
description: ImageSaveOptions mülk. için işleme modunu ve kalitesini belirlemeye izin verir.Graphics nesne.
type: docs
weight: 20
url: /tr/net/aspose.words.saving/imagesaveoptions/graphicsqualityoptions/
---
## ImageSaveOptions.GraphicsQualityOptions property

için işleme modunu ve kalitesini belirlemeye izin verir.Graphics nesne.

```csharp
public GraphicsQualityOptions GraphicsQualityOptions { get; set; }
```

### Notlar

Aspose.Words motoru tarafından varsayılan olarak sağlanan Grafik ayarlarını geçersiz kılmak için bu özelliği kullanın.

Yalnızca bir belge görüntü benzeri bir biçimde kaydedilirken etkili olacaktır.

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

* class [GraphicsQualityOptions](../../graphicsqualityoptions/)
* class [ImageSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../imagesaveoptions/)
* toplantı [Aspose.Words](../../../)


