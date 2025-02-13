---
title: ImageSize.VerticalResolution
second_title: Aspose.Words for .NET API Referansı
description: ImageSize mülk. Dikey çözünürlüğü DPI olarak alır.
type: docs
weight: 50
url: /tr/net/aspose.words.drawing/imagesize/verticalresolution/
---
## ImageSize.VerticalResolution property

Dikey çözünürlüğü DPI olarak alır.

```csharp
public double VerticalResolution { get; }
```

### Örnekler

Şekildeki bir görüntünün özelliklerinin nasıl okunacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Yerel dosya sistemimizden alınan bir resmi içeren belgeye bir şekil ekleyin.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

// Şekil bir resim içeriyorsa, ImageData özelliği geçerli olacaktır,
// ve bir ImageSize nesnesi içerecek.
ImageSize imageSize = shape.ImageData.ImageSize; 

// ImageSize nesnesi, şekil içindeki görüntü hakkında salt okunur bilgileri içerir.
Assert.AreEqual(400, imageSize.HeightPixels);
Assert.AreEqual(400, imageSize.WidthPixels);

const double delta = 0.05;
Assert.AreEqual(95.98d, imageSize.HorizontalResolution, delta);
Assert.AreEqual(95.98d, imageSize.VerticalResolution, delta);

// Resmin gerilmesini önlemek için şeklin boyutunu resmin boyutuna dayandırabiliriz.
shape.Width = imageSize.WidthPoints * 2;
shape.Height = imageSize.HeightPoints * 2;

doc.Save(ArtifactsDir + "Drawing.ImageSize.docx");
```

### Ayrıca bakınız

* class [ImageSize](../)
* ad alanı [Aspose.Words.Drawing](../../imagesize/)
* toplantı [Aspose.Words](../../../)


