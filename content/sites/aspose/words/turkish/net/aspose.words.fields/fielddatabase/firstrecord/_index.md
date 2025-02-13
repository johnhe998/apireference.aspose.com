---
title: FieldDatabase.FirstRecord
second_title: Aspose.Words for .NET API Referansı
description: FieldDatabase mülk. Eklenecek ilk veri kaydının integral kayıt numarasını alır veya ayarlar.
type: docs
weight: 40
url: /tr/net/aspose.words.fields/fielddatabase/firstrecord/
---
## FieldDatabase.FirstRecord property

Eklenecek ilk veri kaydının integral kayıt numarasını alır veya ayarlar.

```csharp
public string FirstRecord { get; set; }
```

### Örnekler

Bir veritabanından nasıl veri alınacağını ve bir belgeye alan olarak nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bu DATABASE alanı, bir veritabanı üzerinde bir sorgu çalıştıracak ve sonucu bir tabloda gösterecektir.
FieldDatabase field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query = "SELECT * FROM [Products]";

Assert.AreEqual($" DATABASE  \\d \"{DatabaseDir.Replace("\\", "\\\\") + "Northwind.mdb"}\" \\c \"DSN=MS Access Databases\" \\s \"SELECT * FROM [Products]\"", 
    field.GetFieldCode());

// Tüm ürünleri brüt satışlara göre azalan düzende sıralayan daha karmaşık bir sorguya sahip başka bir DATABASE alanı ekleyin.
field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query =
    "SELECT [Products].ProductName, FORMAT(SUM([Order Details].UnitPrice * (1 - [Order Details].Discount) * [Order Details].Quantity), 'Currency') AS GrossSales " +
    "FROM([Products] " +
    "LEFT JOIN[Order Details] ON[Products].[ProductID] = [Order Details].[ProductID]) " +
    "GROUP BY[Products].ProductName " +
    "ORDER BY SUM([Order Details].UnitPrice* (1 - [Order Details].Discount) * [Order Details].Quantity) DESC";

// Bu özellikler, LIMIT ve TOP yan tümceleri ile aynı işleve sahiptir.
// Alan tablosunda sorgu sonucunun yalnızca 1'den 10'a kadar olan satırlarını görüntüleyecek şekilde yapılandırın.
field.FirstRecord = "1";
field.LastRecord = "10";

// Bu özellik, tablomuz için kullanmak istediğimiz formatın indeksidir. Tablo biçimlerinin listesi "Tablo Otomatik Biçimi..." menüsündedir.
// Microsoft Word'de bir DATABASE alanı oluşturduğumuzda ortaya çıkıyor. Dizin #10, "Renkli 3" biçimine karşılık gelir.
field.TableFormat = "10";

// FormatAttribute özelliği, birden çok bayrağı saklayan bir tamsayının dize temsilidir.
// TableFormat özelliğinin gösterdiği formatı bu özellikte farklı flaglar ayarlayarak patrially uygulayabiliriz.
// Kullandığımız sayı, tablo stilinin farklı yönlerine karşılık gelen değerlerin birleşiminin toplamıdır.
// 63, 1 (kenarlıklar) + 2 (gölgeleme) + 4 (yazı tipi) + 8 (renk) + 16 (otomatik sığdırma) + 32'yi (başlık satırları) temsil eder.
field.FormatAttributes = "63";
field.InsertHeadings = true;
field.InsertOnceOnMailMerge = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATABASE.docx");
```

### Ayrıca bakınız

* class [FieldDatabase](../)
* ad alanı [Aspose.Words.Fields](../../fielddatabase/)
* toplantı [Aspose.Words](../../../)


