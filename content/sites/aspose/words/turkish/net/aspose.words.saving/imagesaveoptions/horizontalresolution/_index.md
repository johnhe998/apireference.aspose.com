---
title: ImageSaveOptions.HorizontalResolution
second_title: Aspose.Words for .NET API Referansı
description: ImageSaveOptions mülk. Oluşturulan görüntülerin yatay çözünürlüğünü inç başına nokta olarak alır veya ayarlar.
type: docs
weight: 30
url: /tr/net/aspose.words.saving/imagesaveoptions/horizontalresolution/
---
## ImageSaveOptions.HorizontalResolution property

Oluşturulan görüntülerin yatay çözünürlüğünü inç başına nokta olarak alır veya ayarlar.

```csharp
public float HorizontalResolution { get; set; }
```

### Notlar

Bu özellik yalnızca taramalı görüntü biçimlerine kaydederken etkilidir ve çıktı boyutunu piksel cinsinden etkiler.

Varsayılan değer 96'dır.

### Örnekler

Aspose.Words bir belgeyi bir belgeye dönüştürürken görüntünün nasıl düzenleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Belgeyi bir resim olarak kaydettiğimizde, bir SaveOptions nesnesini şuraya aktarabiliriz:
// kaydetme işlemi onu oluştururken görüntüyü düzenleyin.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png)
{
    // Görüntünün parlaklığını ve kontrastını değiştirmek için bu özellikleri ayarlayabiliriz.
    // Her ikisi de 0-1 ölçeğindedir ve varsayılan olarak 0,5'tedir.
    ImageBrightness = 0.3f,
    ImageContrast = 0.7f,

    // Bu özellikler ile yatay ve dikey çözünürlüğü ayarlayabiliriz.
    // Bu, görüntünün boyutlarını etkiler.
    // Bu özellikler için varsayılan değer, 96dpi çözünürlük için 96.0'dır.
    HorizontalResolution = 72f,
    VerticalResolution = 72f,

    // Bu özelliği kullanarak görüntüyü ölçekleyebiliriz. %100 ölçekleme için varsayılan değer 1.0'dır.
    // Çözünürlüğü değiştirmenin neden olacağı görüntü boyutlarındaki değişiklikleri reddetmek için bu özelliği kullanabiliriz.
    Scale = 96f / 72f
};

doc.Save(ArtifactsDir + "ImageSaveOptions.EditImage.png", options);
```

### Ayrıca bakınız

* class [ImageSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../imagesaveoptions/)
* toplantı [Aspose.Words](../../../)


