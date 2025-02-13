---
title: ImageSaveOptions.ImageContrast
second_title: Aspose.Words for .NET API Referansı
description: ImageSaveOptions mülk. Oluşturulan görüntülerin kontrastını alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.saving/imagesaveoptions/imagecontrast/
---
## ImageSaveOptions.ImageContrast property

Oluşturulan görüntülerin kontrastını alır veya ayarlar.

```csharp
public float ImageContrast { get; set; }
```

### Notlar

Bu özellik yalnızca raster görüntü biçimlerine kaydederken etkilidir.

Varsayılan değer 0,5'tir. Değer 0 ile 1 arasında olmalıdır.

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


