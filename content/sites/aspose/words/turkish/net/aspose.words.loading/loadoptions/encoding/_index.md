---
title: LoadOptions.Encoding
second_title: Aspose.Words for .NET API Referansı
description: LoadOptions mülk. Belge içinde kodlama belirtilmemişse bir HTML TXT veya CHM belgesini yüklemek için kullanılacak kodlamayı alır veya ayarlar. Boş olabilir. Varsayılan null.
type: docs
weight: 50
url: /tr/net/aspose.words.loading/loadoptions/encoding/
---
## LoadOptions.Encoding property

Belge içinde kodlama belirtilmemişse bir HTML, TXT veya CHM belgesini yüklemek için kullanılacak kodlamayı alır veya ayarlar. Boş olabilir. Varsayılan null.

```csharp
public Encoding Encoding { get; set; }
```

### Notlar

Bu özellik yalnızca HTML, TXT veya CHM belgeleri yüklenirken kullanılır.

Belge içinde kodlama belirtilmemişse ve bu özellik`hükümsüz`, ardından sistem, kodlamayı otomatik olarak algılamak için deneyecektir.

### Örnekler

Bir belgenin açılacağı kodlamanın nasıl ayarlanacağını gösterir.

```csharp
// Bir FileFormatInfo nesnesi, bu dosyanın UTF-7 dışında bir şeyde kodlanmış olduğunu algılayacaktır.
FileFormatInfo fileFormatInfo = FileFormatUtil.DetectFileFormat(MyDir + "Encoded in UTF-7.txt");

Assert.AreNotEqual(Encoding.UTF7, fileFormatInfo.Encoding);

// Belgeyi yükleme konfigürasyonları olmadan yüklersek, Aspose.Words onun kodlamasını UTF-8 olarak algılayacaktır.
Document doc = new Document(MyDir + "Encoded in UTF-7.txt");

// UTF-8'de ayrıştırılan içerikler geçerli bir dize oluşturur.
// Ancak dosyanın UTF-7'de olduğunu bilerek sonucun yanlış olduğunu görebiliriz.
Assert.AreEqual("Hello world+ACE-", doc.ToString(SaveFormat.Text).Trim());

// Bunun gibi belirsiz kodlama durumlarında, belirli bir kodlama değişkeni ayarlayabiliriz
// dosyayı bir LoadOptions nesnesi içinde ayrıştırmak için.
LoadOptions loadOptions = new LoadOptions
{
    Encoding = Encoding.UTF7
};

// LoadOptions nesnesini geçerken belgeyi yükleyin, ardından belgenin içeriğini doğrulayın.
doc = new Document(MyDir + "Encoded in UTF-7.txt", loadOptions);

Assert.AreEqual("Hello world!", doc.ToString(SaveFormat.Text).Trim());
```

### Ayrıca bakınız

* class [LoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../loadoptions/)
* toplantı [Aspose.Words](../../../)


