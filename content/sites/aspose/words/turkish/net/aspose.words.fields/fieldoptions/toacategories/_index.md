---
title: FieldOptions.ToaCategories
second_title: Aspose.Words for .NET API Referansı
description: FieldOptions mülk. Yetkili kategorilerinin tablosunu alır veya ayarlar.
type: docs
weight: 180
url: /tr/net/aspose.words.fields/fieldoptions/toacategories/
---
## FieldOptions.ToaCategories property

Yetkili kategorilerinin tablosunu alır veya ayarlar.

```csharp
public ToaCategories ToaCategories { get; set; }
```

### Örnekler

TOA alanları için bir kategori kümesinin nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// TOA alanları, girişlerini bu koleksiyonda tanımlanan kategorilere göre filtreleyebilir.
ToaCategories toaCategories = new ToaCategories();
doc.FieldOptions.ToaCategories = toaCategories;

// Bu kategori koleksiyonu, üzerine özel değerler yazabileceğimiz varsayılan değerlerle birlikte gelir.
Assert.AreEqual("Cases", toaCategories[1]);
Assert.AreEqual("Statutes", toaCategories[2]);

toaCategories[1] = "My Category 1";
toaCategories[2] = "My Category 2";

// Varsayılan değerlere bu koleksiyon üzerinden her zaman erişebiliriz.
Assert.AreEqual("Cases", ToaCategories.DefaultCategories[1]);
Assert.AreEqual("Statutes", ToaCategories.DefaultCategories[2]);

// 2 TOA alanı ekleyin. TOA alanları, belgedeki her TA alanı için bir giriş oluşturur.
// Koleksiyonumuzdan bir kategorinin indeksini seçmek için "\c" anahtarını kullanın.
// Bu anahtarla, bir TOA alanı yalnızca TA alanlarından girişleri alır.
// aynı zamanda eşleşen bir kategori indeksine sahip bir "\c" anahtarına sahip. Her bir TOA alanı aynı zamanda
// "\c" anahtarının işaret ettiği kategorinin adı.
builder.InsertField("TOA \\c 1 \\h", null);
builder.InsertField("TOA \\c 2 \\h", null);
builder.InsertBreak(BreakType.PageBreak);

// TOA girişlerini 2 kategoriye ekleyin. İlk TOA alanımız bir giriş alacak,
// "\c" anahtarı aynı zamanda birinci kategoriye işaret eden ikinci TA alanından.
// İkinci TOA alanı, diğer iki TA alanından iki girişe sahip olacaktır.
builder.InsertField("TA \\c 2 \\l \"entry 1\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 1 \\l \"entry 2\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 2 \\l \"entry 3\"");

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.TOA.Categories.docx");
```

### Ayrıca bakınız

* class [ToaCategories](../../toacategories/)
* class [FieldOptions](../)
* ad alanı [Aspose.Words.Fields](../../fieldoptions/)
* toplantı [Aspose.Words](../../../)


