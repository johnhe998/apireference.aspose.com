---
title: ShapeBase.Height
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. Şeklin içerdiği bloğun yüksekliğini alır veya ayarlar.
type: docs
weight: 200
url: /tr/net/aspose.words.drawing/shapebase/height/
---
## ShapeBase.Height property

Şeklin içerdiği bloğun yüksekliğini alır veya ayarlar.

```csharp
public double Height { get; set; }
```

### Notlar

Üst düzey bir şekil için değer puan cinsindendir.

Bir gruptaki şekiller için değer, üst grubun koordinat uzayında ve birimlerindedir.

Varsayılan değer 0'dır.

### Örnekler

Yüzen bir görüntünün nasıl ekleneceğini ve konumunu ve boyutunun nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;

// "Left" özelliğinin değerini işlemek için şeklin "RelativeHorizontalPosition" özelliğini yapılandırın
 // şeklin sayfanın sol tarafından nokta cinsinden yatay mesafesi olarak.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;

// Şeklin sayfanın sol tarafından yatay mesafesini 100 olarak ayarlayın.
shape.Left = 100;

// Şekli 80pt sayfanın üst kısmından aşağıya konumlandırmak için "RelativeVerticalPosition" özelliğini benzer şekilde kullanın.
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Top = 80;

// Boyutları korumak için genişliği otomatik olarak ölçekleyecek şeklin yüksekliğini ayarlayın.
shape.Height = 125;

Assert.AreEqual(125.0d, shape.Width);

// "Bottom" ve "Right" özellikleri görüntünün alt ve sağ kenarlarını içerir.
Assert.AreEqual(shape.Top + shape.Height, shape.Bottom);
Assert.AreEqual(shape.Left + shape.Width, shape.Right);

doc.Save(ArtifactsDir + "Image.CreateFloatingPositionSize.docx");
```

Bir şeklin bir görüntüyle nasıl yeniden boyutlandırılacağını gösterir.

```csharp
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            // "InsertImage" yöntemini kullanarak bir görüntü eklediğimizde, oluşturucu görüntüyü görüntüleyen şekli ölçekler, böylece,
            // Microsoft Word'de %100 yakınlaştırma kullanarak belgeyi görüntülediğimizde şekil, resmi gerçek boyutunda gösteriyor.
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

            // 400x400 resim, 300x300pt resim boyutunda bir ImageData nesnesi oluşturacaktır.
            ImageSize imageSize = shape.ImageData.ImageSize;

            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Bir şeklin boyutları, görüntü verilerinin boyutlarıyla eşleşiyorsa,
            // daha sonra şekil, görüntüyü orijinal boyutunda gösteriyor.
            Assert.AreEqual(300.0d, shape.Width);
            Assert.AreEqual(300.0d, shape.Height);

             // Şeklin toplam boyutunu %50 küçült.
            shape.Width *= 0.5;

             // Ölçekleme faktörleri, şeklin orantılarını korumak için hem genişlik hem de yükseklik için aynı anda geçerlidir.
            Assert.AreEqual(150.0d, shape.Width);
            Assert.AreEqual(150.0d, shape.Height);

            // Şekli yeniden boyutlandırdığımızda, görüntü verilerinin boyutu aynı kalır.
            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Resmin boyutuna göre bir ölçekleme uygulamak için resim veri boyutlarına başvurabiliriz.
            shape.Width = imageSize.WidthPoints * 1.1;

            Assert.AreEqual(330.0d, shape.Width);
            Assert.AreEqual(330.0d, shape.Height);

            doc.Save(ArtifactsDir + "Image.ScaleImage.docx");
```

### Ayrıca bakınız

* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


