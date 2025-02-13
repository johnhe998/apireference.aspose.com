---
title: Watermark.SetImage
second_title: Aspose.Words for .NET API Referansı
description: Watermark yöntem. Belgeye Resim filigranı ekler.
type: docs
weight: 30
url: /tr/net/aspose.words/watermark/setimage/
---
## SetImage(Image) {#setimage}

Belgeye Resim filigranı ekler.

```csharp
public void SetImage(Image image)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| image | Image | Filigran olarak görüntülenen resim. |

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentNullException | Görüntü boş olduğunda atar. |

### Ayrıca bakınız

* class [Watermark](../)
* ad alanı [Aspose.Words](../../watermark/)
* toplantı [Aspose.Words](../../../)

---

## SetImage(Image, ImageWatermarkOptions) {#setimage_1}

Belgeye Resim filigranı ekler.

```csharp
public void SetImage(Image image, ImageWatermarkOptions options)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| image | Image | Filigran olarak görüntülenen resim. |
| options | ImageWatermarkOptions | Görüntü filigranı için ek seçenekleri tanımlar. |

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentNullException | Görüntü boş olduğunda atar. |

### Notlar

Eğer[`ImageWatermarkOptions`](../../imagewatermarkoptions/) null ise filigran varsayılan seçeneklerle ayarlanacaktır.

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

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* ad alanı [Aspose.Words](../../watermark/)
* toplantı [Aspose.Words](../../../)

---

## SetImage(string, ImageWatermarkOptions) {#setimage_2}

Belgeye Resim filigranı ekler.

```csharp
public void SetImage(string imagePath, ImageWatermarkOptions options)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| imagePath | String | Filigran olarak görüntülenen görüntü dosyasının yolu. |
| options | ImageWatermarkOptions | Görüntü filigranı için ek seçenekleri tanımlar. |

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentNullException | Yol boş olduğunda atar. |

### Notlar

Eğer[`ImageWatermarkOptions`](../../imagewatermarkoptions/) null ise filigran varsayılan seçeneklerle ayarlanacaktır.

### Ayrıca bakınız

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* ad alanı [Aspose.Words](../../watermark/)
* toplantı [Aspose.Words](../../../)


