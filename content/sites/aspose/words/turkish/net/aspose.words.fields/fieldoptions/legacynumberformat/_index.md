---
title: FieldOptions.LegacyNumberFormat
second_title: Aspose.Words for .NET API Referansı
description: FieldOptions mülk. Alanlar için eski AW 13.10dan erken sayı biçiminin etkinleştirilip etkinleştirilmediğini gösteren değeri alır veya ayarlar.
type: docs
weight: 140
url: /tr/net/aspose.words.fields/fieldoptions/legacynumberformat/
---
## FieldOptions.LegacyNumberFormat property

Alanlar için eski (AW 13.10'dan erken) sayı biçiminin etkinleştirilip etkinleştirilmediğini gösteren değeri alır veya ayarlar.

```csharp
public bool LegacyNumberFormat { get; set; }
```

### Notlar

Bu özellik olarak ayarlandığında **doğru**, şablon sembolü "#" .net: 'de olduğu gibi çalıştı, varsa kare işaretini karşılık gelen rakamla değiştirir; aksi takdirde sonuç dizisinde hiçbir sembol görünmez.

Bu özellik olarak ayarlandığında **yanlış**, şablon simgesi "#" MS Word olarak çalışır: Bu biçim öğesi, sonuçta görüntülenecek gerekli sayısal yerleri belirtir. Sonuç o yerde bir rakam içermiyorsa, MS Word bir boşluk görüntüler. Örneğin, { = 9 + 6 \# $### } 15 $ görüntüler.

Varsayılan değer **yanlış**.

### Örnekler

Alanlar için eski sayı biçimlendirmesinin nasıl etkinleştirildiğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("= 2 + 3 \\# $##");

Assert.AreEqual("$ 5", field.Result);

doc.FieldOptions.LegacyNumberFormat = true;
field.Update();

Assert.AreEqual("$5", field.Result);
```

### Ayrıca bakınız

* class [FieldOptions](../)
* ad alanı [Aspose.Words.Fields](../../fieldoptions/)
* toplantı [Aspose.Words](../../../)


