---
title: ImageWatermarkOptions.IsWashout
second_title: Aspose.Words for .NET API Referansı
description: ImageWatermarkOptions mülk. Filigranın silinme etkisinden sorumlu bir boole değeri alır veya ayarlar. Varsayılan değer Truedur.
type: docs
weight: 20
url: /tr/net/aspose.words/imagewatermarkoptions/iswashout/
---
## ImageWatermarkOptions.IsWashout property

Filigranın silinme etkisinden sorumlu bir boole değeri alır veya ayarlar. Varsayılan değer True'dur.

```csharp
public bool IsWashout { get; set; }
```

### Örnekler

Yerel dosya sistemindeki bir görüntüden nasıl filigran oluşturulacağını gösterir.

```csharp
Document doc = new Document();

            // Görüntü filigranının görünümünü bir ImageWatermarkOptions nesnesiyle değiştirin,
            // daha sonra bir görüntü dosyasından bir filigran oluştururken iletin.
            ImageWatermarkOptions imageWatermarkOptions = new ImageWatermarkOptions();
            imageWatermarkOptions.Scale = 5;
            imageWatermarkOptions.IsWashout = false;

#if NET48 || JAVA
            doc.Watermark.SetImage(Image.FromFile(ImageDir + "Logo.jpg"), imageWatermarkOptions);
#elif NET5_0_OR_GREATER || __MOBILE__
            using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
            {
                doc.Watermark.SetImage(image, imageWatermarkOptions);
            }
#endif

            doc.Save(ArtifactsDir + "Document.ImageWatermark.docx");
```

### Ayrıca bakınız

* class [ImageWatermarkOptions](../)
* ad alanı [Aspose.Words](../../imagewatermarkoptions/)
* toplantı [Aspose.Words](../../../)


