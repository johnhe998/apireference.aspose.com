---
title: Enum FieldUpdateCultureSource
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fields.FieldUpdateCultureSource Sıralama. Alan güncellemesi sırasında hangi kültürün kullanılacağını gösterir.
type: docs
weight: 2410
url: /tr/net/aspose.words.fields/fieldupdateculturesource/
---
## FieldUpdateCultureSource enumeration

Alan güncellemesi sırasında hangi kültürün kullanılacağını gösterir.

```csharp
public enum FieldUpdateCultureSource
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| CurrentThread | `0` | Geçerli yürütme iş parçacığının kültürü, alanları güncellemek için kullanılır. |
| FieldCode | `1` | Alan biçimlendirme özelliklerinde dil ayarı aracılığıyla belirtilen kültür kullanılır. |

### Örnekler

Alan güncellemesi veya adres mektup birleştirme sırasında tarih biçimlendirmesi için kullanılan kültürün kaynağının nasıl belirtileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Almanca yerel ayarıyla iki birleştirme alanı ekleyin.
builder.Font.LocaleId = new CultureInfo("de-DE").LCID;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

// Bir değişkende orijinal değerini koruduktan sonra geçerli kültürü ABD İngilizcesine ayarlayın.
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");

// Bu birleştirme, tarihi biçimlendirmek için geçerli iş parçacığının kültürünü kullanır, ABD İngilizcesi.
doc.MailMerge.Execute(new[] { "Date1" }, new object[] { new DateTime(2020, 1, 01) });

// Kültür değerini alan kodundan kaynaklamak için sonraki birleştirmeyi yapılandırın. O kültürün değeri Alman olacaktır.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.MailMerge.Execute(new[] { "Date2" }, new object[] { new DateTime(2020, 1, 01) });

// İlk birleştirme sonucu İngilizce olarak biçimlendirilmiş bir tarih içerirken, ikincisi Almancadır.
Assert.AreEqual("Wednesday, 1 January 2020 - Mittwoch, 1 Januar 2020", doc.Range.Text.Trim());

// İş parçacığının orijinal kültürünü geri yükleyin.
Thread.CurrentThread.CurrentCulture = currentCulture;
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Fields](../../aspose.words.fields/)
* toplantı [Aspose.Words](../../)


