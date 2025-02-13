---
title: ImageSaveOptions.ImageSaveOptions
second_title: Aspose.Words for .NET API Referansı
description: ImageSaveOptions inşaatçı. İşlenen görüntüleri the içine kaydetmek için kullanılabilecek bu sınıfın yeni bir örneğini başlatırTiff Png Bmp  Emf Jpeg veyaSvg biçim. Png Bmp Jpeg veyaSvg biçim.
type: docs
weight: 10
url: /tr/net/aspose.words.saving/imagesaveoptions/imagesaveoptions/
---
## ImageSaveOptions constructor

İşlenen görüntüleri the içine kaydetmek için kullanılabilecek bu sınıfın yeni bir örneğini başlatırTiff ,Png ,Bmp , Emf ,Jpeg veyaSvg biçim. Png ,Bmp ,Jpeg veyaSvg biçim.

```csharp
public ImageSaveOptions(SaveFormat saveFormat)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| saveFormat | SaveFormat | olabilirTiff ,Png ,Bmp , Emf ,Jpeg veyaSvg . Png ,Bmp ,Jpeg veyaSvg . |

### Örnekler

Bir belgeyi JPEG olarak kaydederken sıkıştırmanın nasıl yapılandırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertImage(ImageDir + "Logo.jpg");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "ImageSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi bir görüntüye dönüştürme şeklini değiştirmek için.
ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Jpeg);

// Belgeyi oluştururken daha güçlü sıkıştırma kullanmak için "JpegQuality" özelliğini "10" olarak ayarlayın.
// Bu, belgenin dosya boyutunu küçültecek, ancak görüntü daha belirgin sıkıştırma yapaylıkları gösterecektir.
imageOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg", imageOptions);

Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg").Length));

// Belgeyi işlerken daha zayıf sıkıştırma kullanmak için "JpegQuality" özelliğini "100" olarak ayarlayın.
// Bu, artan dosya boyutu pahasına görüntünün kalitesini artıracaktır.
imageOptions.JpegQuality = 100;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg", imageOptions);

Assert.That(60000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg").Length));
```

### Ayrıca bakınız

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [ImageSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../imagesaveoptions/)
* toplantı [Aspose.Words](../../../)


