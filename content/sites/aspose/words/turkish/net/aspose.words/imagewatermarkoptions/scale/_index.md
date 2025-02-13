---
title: ImageWatermarkOptions.Scale
second_title: Aspose.Words for .NET API Referansı
description: ImageWatermarkOptions mülk. Görüntünün bir bölümü olarak ifade edilen ölçek faktörünü alır veya ayarlar. Varsayılan değer 0  auto.
type: docs
weight: 30
url: /tr/net/aspose.words/imagewatermarkoptions/scale/
---
## ImageWatermarkOptions.Scale property

Görüntünün bir bölümü olarak ifade edilen ölçek faktörünü alır veya ayarlar. Varsayılan değer 0 - auto.

```csharp
public double Scale { get; set; }
```

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentOutOfRangeException | Bağımsız değişken geçerli değerler aralığının dışında olduğunda atar. |

### Notlar

Geçerli değerler 0 ile 65.5 arasında değişir.

Otomatik ölçeklendirme, filigranın sayfa kenar boşluklarına göre maksimum genişliğine ve maksimum yüksekliğine ölçekleneceği anlamına gelir.

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


