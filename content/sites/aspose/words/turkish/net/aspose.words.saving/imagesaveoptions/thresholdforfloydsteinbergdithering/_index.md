---
title: ImageSaveOptions.ThresholdForFloydSteinbergDithering
second_title: Aspose.Words for .NET API Referansı
description: ImageSaveOptions mülk. FloydSteinberg yöntemindeki ikilileştirme hatasının değerini belirleyen eşiği alır veya ayarlar. ImageBinarizationMethod ImageBinarizationMethod.FloydSteinbergDithering. dir
type: docs
weight: 150
url: /tr/net/aspose.words.saving/imagesaveoptions/thresholdforfloydsteinbergdithering/
---
## ImageSaveOptions.ThresholdForFloydSteinbergDithering property

Floyd-Steinberg yöntemindeki ikilileştirme hatasının değerini belirleyen eşiği alır veya ayarlar. [`ImageBinarizationMethod`](../../imagebinarizationmethod/) ImageBinarizationMethod.FloydSteinbergDithering. 'dir

```csharp
public byte ThresholdForFloydSteinbergDithering { get; set; }
```

### Notlar

Varsayılan değer 128'dir.

### Örnekler

Bir TIFF görüntüsü oluşturmak için Floyd-Steinberg yöntemini kullanırken TIFF ikilileştirme hata eşiğinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Belgeyi TIFF olarak kaydettiğimizde, bir SaveOptions nesnesini şuraya aktarabiliriz:
// Aspose.Words'ün bu görüntüyü oluştururken uygulayacağı renk taklidini ayarlayın.
// "ThresholdForFloydSteinbergDithering" özelliğinin varsayılan değeri 128'dir.
// Daha yüksek değerler daha koyu görüntüler üretme eğilimindedir.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff)
{
    TiffCompression = TiffCompression.Ccitt3,
    TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
    ThresholdForFloydSteinbergDithering = 240
};

doc.Save(ArtifactsDir + "ImageSaveOptions.FloydSteinbergDithering.tiff", options);
```

### Ayrıca bakınız

* class [ImageSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../imagesaveoptions/)
* toplantı [Aspose.Words](../../../)


