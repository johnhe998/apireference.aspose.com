---
title: HtmlSaveOptions.ScaleImageToShapeSize
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. HTML MHTML veya EPUBa dışa aktarılırken görüntülerin Aspose.Words tarafından sınırlayıcı şekil boyutuna ölçeklenip ölçeklenmediğini belirtir. Varsayılan değerdoğru .
type: docs
weight: 450
url: /tr/net/aspose.words.saving/htmlsaveoptions/scaleimagetoshapesize/
---
## HtmlSaveOptions.ScaleImageToShapeSize property

HTML, MHTML veya EPUB'a dışa aktarılırken görüntülerin Aspose.Words tarafından sınırlayıcı şekil boyutuna ölçeklenip ölçeklenmediğini belirtir. Varsayılan değer`doğru` .

```csharp
public bool ScaleImageToShapeSize { get; set; }
```

### Notlar

Microsoft Word belgesindeki bir görüntü bir şekildir. Şeklin bir boyutu vardır ve image kendi boyutuna sahiptir. Boyutlar doğrudan bağlantılı değildir. Örneğin, resim 1024x786 piksel, olabilir, ancak bu resmi gösteren şekil 400x300 nokta olabilir.

Tarayıcıda bir resmi görüntülemek için, şekil boyutuna ölçeklendirilmelidir. `ScaleImageToShapeSize` özellik, image 'nin ölçeklenmesinin nerede gerçekleştiğini kontrol eder: HTML'ye dışa aktarma sırasında Aspose.Words'de veya belgeyi görüntülerken tarayıcıda.

Ne zaman`ScaleImageToShapeSize` dır-dir`doğru` , görüntü, HTML'ye dışa aktarma sırasında yüksek kaliteli ölçekleme kullanılarak Aspose.Words tarafından ölçeklenir. Ne zaman`ScaleImageToShapeSize``yanlış`görüntü orijinal boyutuyla çıkar ve tarayıcının onu ölçeklendirmesi gerekir.

Genel olarak, tarayıcılar hızlı ve düşük kaliteli ölçekleme yapar. Sonuç olarak, tarayıcıda normalde daha iyi görüntü kalitesi ve aşağıdaki durumlarda daha küçük dosya boyutu elde edersiniz.`ScaleImageToShapeSize` dır-dir`doğru` , ancak daha iyi baskı kalitesi ve daha hızlı dönüştürme`ScaleImageToShapeSize` dır-dir`yanlış`.

### Örnekler

.html'ye kaydederken görüntülerin üst şekil boyutlarına ölçeklendirilmesinin nasıl devre dışı bırakılacağını gösterir.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            // Görüntü içeren bir şekil ekleyin ve ardından bu şekli görüntüden önemli ölçüde küçültün.
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Transparent background logo.png");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            Shape imageShape = builder.InsertImage(image);
            imageShape.Width = 50;
            imageShape.Height = 50;

            // Resimli şekiller içeren bir belgeyi HTML'ye kaydetmek, yerel dosya sisteminde bir resim dosyası oluşturacaktır.
            // bu tür her şekil için. Çıktı HTML belgesinde <image> bu görüntülere bağlantı vermek ve bunları görüntülemek için etiketler.
            // Belgeyi HTML'ye kaydettiğimizde, belirlemek için bir SaveOptions nesnesi iletebiliriz.
            // şekillerin içindeki tüm resimlerin şekillerinin boyutlarına ölçeklenip ölçeklendirilmeyeceği.
            // "ScaleImageToShapeSize" bayrağının "true" olarak ayarlanması her görüntüyü küçültür
            // kaydedilen hiçbir görüntünün belgenin gerektirdiğinden daha büyük olmaması için, onu içeren şeklin boyutuna.
            // "ScaleImageToShapeSize" bayrağının "false" olarak ayarlanması bu resimlerin orijinal boyutlarını koruyacaktır,
            // görüntü kalitesini korumak karşılığında daha fazla yer kaplayacak.
            HtmlSaveOptions options = new HtmlSaveOptions { ScaleImageToShapeSize = scaleImageToShapeSize };

            doc.Save(ArtifactsDir + "HtmlSaveOptions.ScaleImageToShapeSize.html", options);

            FileInfo fileInfo = new FileInfo(ArtifactsDir + "HtmlSaveOptions.ScaleImageToShapeSize.001.png");

#if NET48 || JAVA
        if (scaleImageToShapeSize)
            Assert.That(3000, Is.AtLeast(fileInfo.Length));
        else
            Assert.That(20000, Is.LessThan(fileInfo.Length));
#elif NET5_0_OR_GREATER
        if (scaleImageToShapeSize)
            Assert.That(10000, Is.AtLeast(fileInfo.Length));
        else
            Assert.That(30000, Is.LessThan(fileInfo.Length));
#endif
```

### Ayrıca bakınız

* property [ImageResolution](../imageresolution/)
* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


