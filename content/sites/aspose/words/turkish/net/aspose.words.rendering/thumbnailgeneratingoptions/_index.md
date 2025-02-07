---
title: Class ThumbnailGeneratingOptions
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Rendering.ThumbnailGeneratingOptions sınıf. Bir belge için küçük resim oluşturulurken ek seçenekleri belirtmek için kullanılabilir.
type: docs
weight: 4340
url: /tr/net/aspose.words.rendering/thumbnailgeneratingoptions/
---
## ThumbnailGeneratingOptions class

Bir belge için küçük resim oluşturulurken ek seçenekleri belirtmek için kullanılabilir.

```csharp
public class ThumbnailGeneratingOptions
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [ThumbnailGeneratingOptions](thumbnailgeneratingoptions/)() | Default_Constructor |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [GenerateFromFirstPage](../../aspose.words.rendering/thumbnailgeneratingoptions/generatefromfirstpage/) { get; set; } | Belgenin ilk sayfasından mı yoksa ilk görüntüden mi küçük resim oluşturulacağını belirtir. |
| [ThumbnailSize](../../aspose.words.rendering/thumbnailgeneratingoptions/thumbnailsize/) { get; set; } | Oluşturulan küçük resmin piksel cinsinden boyutu. Varsayılan, 600x900'dür. |

### Notlar

Kullanıcı yöntemi çağırabilir[`UpdateThumbnail`](../../aspose.words/document/updatethumbnail/) oluşturmak için[`Thumbnail`](../../aspose.words.properties/builtindocumentproperties/thumbnail/) bir belge için.

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

* ad alanı [Aspose.Words.Rendering](../../aspose.words.rendering/)
* toplantı [Aspose.Words](../../)


