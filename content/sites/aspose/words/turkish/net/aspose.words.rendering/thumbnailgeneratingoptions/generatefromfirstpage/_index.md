---
title: ThumbnailGeneratingOptions.GenerateFromFirstPage
second_title: Aspose.Words for .NET API Referansı
description: ThumbnailGeneratingOptions mülk. Belgenin ilk sayfasından mı yoksa ilk görüntüden mi küçük resim oluşturulacağını belirtir.
type: docs
weight: 20
url: /tr/net/aspose.words.rendering/thumbnailgeneratingoptions/generatefromfirstpage/
---
## ThumbnailGeneratingOptions.GenerateFromFirstPage property

Belgenin ilk sayfasından mı yoksa ilk görüntüden mi küçük resim oluşturulacağını belirtir.

```csharp
public bool GenerateFromFirstPage { get; set; }
```

### Notlar

Varsayılan`doğru` , bu, küçük resmin belgenin ilk sayfasından oluşturulacağı anlamına gelir. Değer`yanlış` ve belgede resim yok, küçük resim belgenin ilk sayfasından oluşturulacak.

### Örnekler

Bir belgenin küçük resminin nasıl güncelleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Bir belgeyi .epub'a kaydederken küçük resim ayarlamanın iki yolu vardır.
// 1 - Belgenin ilk sayfasını kullanın:
doc.UpdateThumbnail();
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstPage.epub");

// 2 - Belgede bulunan ilk resmi kullanın:
ThumbnailGeneratingOptions options = new ThumbnailGeneratingOptions();
options.ThumbnailSize = new Size(400, 400);
options.GenerateFromFirstPage = false;

doc.UpdateThumbnail(options);
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstImage.epub");
```

### Ayrıca bakınız

* class [ThumbnailGeneratingOptions](../)
* ad alanı [Aspose.Words.Rendering](../../thumbnailgeneratingoptions/)
* toplantı [Aspose.Words](../../../)


