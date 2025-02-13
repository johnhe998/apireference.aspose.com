---
title: TxtLoadOptions.DocumentDirection
second_title: Aspose.Words for .NET API Referansı
description: TxtLoadOptions mülk. Bir belge yönünü alır veya ayarlar. Varsayılan değerLeftToRight .
type: docs
weight: 30
url: /tr/net/aspose.words.loading/txtloadoptions/documentdirection/
---
## TxtLoadOptions.DocumentDirection property

Bir belge yönünü alır veya ayarlar. Varsayılan değerLeftToRight .

```csharp
public DocumentDirection DocumentDirection { get; set; }
```

### Örnekler

Düz metin belgesi metin yönünün nasıl algılanacağını gösterir.

```csharp
// Bir belgenin yapıcısına iletebileceğimiz bir "TxtLoadOptions" nesnesi oluşturun
// bir düz metin belgesini nasıl yüklediğimizi değiştirmek için.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// "DocumentDirection" özelliğini "DocumentDirection.Auto" olarak ayarlayın, otomatik olarak algılar
// Aspose.Words'ün düz metinden yüklediği metnin her paragrafının yönü.
// Her paragrafın "Bidi" özelliği, yönünü saklayacaktır.
loadOptions.DocumentDirection = DocumentDirection.Auto;

// İbranice metni sağdan sola olarak algıla.
Document doc = new Document(MyDir + "Hebrew text.txt", loadOptions);

Assert.True(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);

// İngilizce metni sağdan sola olarak algıla.
doc = new Document(MyDir + "English text.txt", loadOptions);

Assert.False(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);
```

### Ayrıca bakınız

* enum [DocumentDirection](../../documentdirection/)
* class [TxtLoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../txtloadoptions/)
* toplantı [Aspose.Words](../../../)


