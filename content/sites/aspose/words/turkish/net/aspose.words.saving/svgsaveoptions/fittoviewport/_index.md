---
title: SvgSaveOptions.FitToViewPort
second_title: Aspose.Words for .NET API Referansı
description: SvgSaveOptions mülk. Çıktı SVGsinin kullanılabilir görünüm alanı alanını tarayıcı penceresi veya kapsayıcı doldurup doldurmayacağını belirtir. Çıktı SVGsinin gerçek genişliği ve yüksekliği 100 olarak ayarlanır.
type: docs
weight: 30
url: /tr/net/aspose.words.saving/svgsaveoptions/fittoviewport/
---
## SvgSaveOptions.FitToViewPort property

Çıktı SVG'sinin kullanılabilir görünüm alanı alanını (tarayıcı penceresi veya kapsayıcı) doldurup doldurmayacağını belirtir. Çıktı SVG'sinin gerçek genişliği ve yüksekliği %100 olarak ayarlanır.

Varsayılan değer yanlıştır.

```csharp
public bool FitToViewPort { get; set; }
```

### Örnekler

Bir .docx belgesini .svg'ye dönüştürürken görüntülerin özelliklerinin nasıl taklit edileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// SvgSaveOptions nesnesini, sayfa kenarlıkları veya seçilebilir metin olmadan kaydedilecek şekilde yapılandırın.
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### Ayrıca bakınız

* class [SvgSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../svgsaveoptions/)
* toplantı [Aspose.Words](../../../)


