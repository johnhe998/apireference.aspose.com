---
title: FieldOptions.UseInvariantCultureNumberFormat
second_title: Aspose.Words for .NET API Referansı
description: FieldOptions mülk. Sayı biçiminin değişmez kültür kullanılarak veya değil kullanılarak ayrıştırıldığını belirten değeri alır veya ayarlar
type: docs
weight: 190
url: /tr/net/aspose.words.fields/fieldoptions/useinvariantculturenumberformat/
---
## FieldOptions.UseInvariantCultureNumberFormat property

Sayı biçiminin değişmez kültür kullanılarak veya değil kullanılarak ayrıştırıldığını belirten değeri alır veya ayarlar

```csharp
public bool UseInvariantCultureNumberFormat { get; set; }
```

### Notlar

Bu özellik olarak ayarlandığında **doğru** , sayı biçimi değişmez bir kültürden alınmıştır.

Bu özellik olarak ayarlandığında **yanlış** sayı biçimi geçerli iş parçacığının kültüründen alınır.

Varsayılan değer **yanlış**.

### Örnekler

Değişmeyen kültüre göre sayıların nasıl biçimlendirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
Field field = builder.InsertField(" = 1234567,89 \\# $#,###,###.##");
field.Update();

// Bazen alanlar, belirli kültürler altında sayılarını doğru biçimde biçimlendirmeyebilir. 
Assert.IsFalse(doc.FieldOptions.UseInvariantCultureNumberFormat);
Assert.AreEqual("$1234567,89 .     ", field.Result);

// Bunu düzeltmek için tüm iş parçacığının kültürünü değiştirebiliriz.
// Bunu düzeltmenin başka bir yolu da bu bayrağı ayarlamaktır,
// sayıları biçimlendirirken değişmez kültürü kullanmak için tüm alanları alır.
// Bu yol, tüm iş parçacığı için kültürü değiştirmekten kaçınmamızı sağlar.
doc.FieldOptions.UseInvariantCultureNumberFormat = true;
field.Update();
Assert.AreEqual("$1.234.567,89", field.Result);
```

### Ayrıca bakınız

* class [FieldOptions](../)
* ad alanı [Aspose.Words.Fields](../../fieldoptions/)
* toplantı [Aspose.Words](../../../)


