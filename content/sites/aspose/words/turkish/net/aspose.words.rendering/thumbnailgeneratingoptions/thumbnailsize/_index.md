---
title: ThumbnailGeneratingOptions.ThumbnailSize
second_title: Aspose.Words for .NET API Referansı
description: ThumbnailGeneratingOptions mülk. Oluşturulan küçük resmin piksel cinsinden boyutu. Varsayılan 600x900dür.
type: docs
weight: 30
url: /tr/net/aspose.words.rendering/thumbnailgeneratingoptions/thumbnailsize/
---
## ThumbnailGeneratingOptions.ThumbnailSize property

Oluşturulan küçük resmin piksel cinsinden boyutu. Varsayılan, 600x900'dür.

```csharp
public Size ThumbnailSize { get; set; }
```

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


