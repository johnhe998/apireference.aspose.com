---
title: FixedPageSaveOptions.JpegQuality
second_title: Aspose.Words for .NET API Referansı
description: FixedPageSaveOptions mülk. Html belgesi içindeki JPEG görüntülerinin kalitesini belirleyen bir değer alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.saving/fixedpagesaveoptions/jpegquality/
---
## FixedPageSaveOptions.JpegQuality property

Html belgesi içindeki JPEG görüntülerinin kalitesini belirleyen bir değer alır veya ayarlar.

```csharp
public int JpegQuality { get; set; }
```

### Notlar

Yalnızca bir belge JPEG görüntüleri içerdiğinde etkilidir.

Sabit sayfa biçiminde kaydederken bir belge içindeki görüntülerin kalitesini almak veya ayarlamak için bu özelliği kullanın. Değer 0 ile 100 arasında değişebilir, burada 0 en kötü kaliteyi, ancak maksimum sıkıştırmayı ve 100 en iyi kaliteyi ancak minimum sıkıştırmayı ifade eder.

Varsayılan değer 95'tir.

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

* class [FixedPageSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* toplantı [Aspose.Words](../../../)


