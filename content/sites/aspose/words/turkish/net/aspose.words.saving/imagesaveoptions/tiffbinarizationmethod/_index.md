---
title: ImageSaveOptions.TiffBinarizationMethod
second_title: Aspose.Words for .NET API Referansı
description: ImageSaveOptions mülk. Görüntüleri 1 bpp formatına dönüştürürken kullanılan yöntemi alır veya ayarlar SaveFormat SaveFormat.Tiff ve dirTiffCompression TiffCompression.Ccitt3 veya TiffCompression.Ccitt4. ye eşittir
type: docs
weight: 160
url: /tr/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/
---
## ImageSaveOptions.TiffBinarizationMethod property

Görüntüleri 1 bpp formatına dönüştürürken kullanılan yöntemi alır veya ayarlar [`SaveFormat`](../saveformat/) SaveFormat.Tiff ve 'dir[`TiffCompression`](../tiffcompression/) TiffCompression.Ccitt3 veya TiffCompression.Ccitt4. 'ye eşittir

```csharp
public ImageBinarizationMethod TiffBinarizationMethod { get; set; }
```

### Notlar

Varsayılan değer ImageBinarizationMethod.Threshold'dur.

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

* enum [ImageBinarizationMethod](../../imagebinarizationmethod/)
* class [ImageSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../imagesaveoptions/)
* toplantı [Aspose.Words](../../../)


