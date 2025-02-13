---
title: Field.LocaleId
second_title: Aspose.Words for .NET API Referansı
description: Field mülk. Alanın LCIDsini alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.fields/field/localeid/
---
## Field.LocaleId property

Alanın LCID'sini alır veya ayarlar.

```csharp
public int LocaleId { get; set; }
```

### Örnekler

Bir alanın nasıl ekleneceğini ve yerel ayarıyla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir TARİH alanı girin ve görüntüleneceği tarihi yazdırın.
// Dizinizin mevcut kültürü, tarihin biçimlendirmesini belirler.
Field field = builder.InsertField(@"DATE");
Console.WriteLine($"Today's date, as displayed in the \"{CultureInfo.CurrentCulture.EnglishName}\" culture: {field.Result}");

Assert.AreEqual(1033, field.LocaleId);
// İş parçacığımızın kültürünü değiştirmek, DATE alanının sonucunu etkileyecektir.
// DATE alanının farklı bir kültürde bir tarihi görüntülemesini sağlamanın bir başka yolu da LocaleId özelliğini kullanmaktır.
// Bu yol, bu etkiyi elde etmek için iş parçacığının kültürünü değiştirmekten kaçınmamızı sağlar.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
CultureInfo de = new CultureInfo("de-DE");
field.LocaleId = de.LCID;
field.Update();

Console.WriteLine($"Today's date, as displayed according to the \"{CultureInfo.GetCultureInfo(field.LocaleId).EnglishName}\" culture: {field.Result}");
```

### Ayrıca bakınız

* class [Field](../)
* ad alanı [Aspose.Words.Fields](../../field/)
* toplantı [Aspose.Words](../../../)


