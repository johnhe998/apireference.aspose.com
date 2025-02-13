---
title: DocumentProperty.ToByteArray
second_title: Aspose.Words for .NET API Referansı
description: DocumentProperty yöntem. Özellik değerini bayt dizisi olarak döndürür.
type: docs
weight: 70
url: /tr/net/aspose.words.properties/documentproperty/tobytearray/
---
## DocumentProperty.ToByteArray method

Özellik değerini bayt dizisi olarak döndürür.

```csharp
public byte[] ToByteArray()
```

### Notlar

Özellik türü değilse bir istisna atarByteArray.

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

* class [DocumentProperty](../)
* ad alanı [Aspose.Words.Properties](../../documentproperty/)
* toplantı [Aspose.Words](../../../)


