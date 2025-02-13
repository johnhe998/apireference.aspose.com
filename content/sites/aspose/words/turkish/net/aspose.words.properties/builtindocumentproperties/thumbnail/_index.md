---
title: BuiltInDocumentProperties.Thumbnail
second_title: Aspose.Words for .NET API Referansı
description: BuiltInDocumentProperties mülk. Belgenin küçük resmini alır veya ayarlar.
type: docs
weight: 280
url: /tr/net/aspose.words.properties/builtindocumentproperties/thumbnail/
---
## BuiltInDocumentProperties.Thumbnail property

Belgenin küçük resmini alır veya ayarlar.

```csharp
public byte[] Thumbnail { get; set; }
```

### Notlar

Şimdilik bu özellik yalnızca bir belge ePub'a aktarılırken kullanılır, diğer belge biçimlerinden okunmaz ve bunlara yazılmaz.

Rastgele formatın görüntüsü bu özelliğe ayarlanabilir, ancak format dışa aktarma sırasında kontrol edilir. InvalidOperationException görüntü geçersizse veya biçimi, belirli belge biçimi için için desteklenmiyorsa atılır.

ePub yayını için yalnızca gif, jpeg ve png görüntüleri kullanılabilir.

### Örnekler

Epub olarak kaydettiğimiz bir belgeye nasıl küçük resim ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// "Thumbnail" özelliği eklediğimiz resim verilerini içeren bir belgeyi Epub olarak kaydedersek,
// o belgeyi açan bir okuyucu, resmi ilk sayfadan önce görüntüleyebilir.
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

byte[] thumbnailBytes = File.ReadAllBytes(ImageDir + "Logo.jpg");
properties.Thumbnail = thumbnailBytes;

doc.Save(ArtifactsDir + "DocumentProperties.Thumbnail.epub");

// Bir belgenin küçük resmini çıkarabilir ve yerel dosya sistemine kaydedebiliriz.
DocumentProperty thumbnail = doc.BuiltInDocumentProperties["Thumbnail"];
File.WriteAllBytes(ArtifactsDir + "DocumentProperties.Thumbnail.gif", thumbnail.ToByteArray());
```

### Ayrıca bakınız

* class [BuiltInDocumentProperties](../)
* ad alanı [Aspose.Words.Properties](../../builtindocumentproperties/)
* toplantı [Aspose.Words](../../../)


