---
title: Enum ImageBinarizationMethod
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.ImageBinarizationMethod Sıralama. Görüntüyü ikili hale getirmek için kullanılan yöntemi belirtir.
type: docs
weight: 4940
url: /tr/net/aspose.words.saving/imagebinarizationmethod/
---
## ImageBinarizationMethod enumeration

Görüntüyü ikili hale getirmek için kullanılan yöntemi belirtir.

```csharp
public enum ImageBinarizationMethod
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Threshold | `0` | Eşik yöntemini belirtir. |
| FloydSteinbergDithering | `1` | Floyd-Steinberg hata yayma yöntemini kullanarak renk taklidini belirtir. |

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

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


