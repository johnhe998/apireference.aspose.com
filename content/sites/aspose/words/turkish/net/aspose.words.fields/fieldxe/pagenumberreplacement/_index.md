---
title: FieldXE.PageNumberReplacement
second_title: Aspose.Words for .NET API Referansı
description: FieldXE mülk. Sayfa numarası yerine kullanılan metni alır veya ayarlar.
type: docs
weight: 50
url: /tr/net/aspose.words.fields/fieldxe/pagenumberreplacement/
---
## FieldXE.PageNumberReplacement property

Sayfa numarası yerine kullanılan metni alır veya ayarlar.

```csharp
public string PageNumberReplacement { get; set; }
```

### Örnekler

Bir INDEX alanında çapraz referansların nasıl tanımlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belgede bulunan her XE alanı için bir giriş görüntüleyecek bir INDEX alanı oluşturun.
// Her giriş, sol tarafta XE alanının Text özellik değerini gösterecek,
// ve sağdaki XE alanını içeren sayfanın numarası.
// INDEX girişi, "Metin" özelliğinde eşleşen değerlere sahip tüm XE alanlarını toplayacaktır.
// her XE alanı için bir giriş yapmak yerine tek bir girişe.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Bir XE alanını, INDEX girişini sayfa numarası yerine bir dize gösterecek şekilde yapılandırabiliriz.
// İlk olarak, sayfa numarasını bir dizeyle değiştiren girişler için,
// XE alanının Metin özelliği değeri ile dize arasında özel bir ayırıcı belirtin.
index.CrossReferenceSeparator = ", see: ";

Assert.AreEqual(" INDEX  \\k \", see: \"", index.GetFieldCode());

// Bu alanın sayfa numarasını görüntüleyen normal bir INDEX girişi oluşturan bir XE alanı ekleyin,
// ve CrossReferenceSeparator değerini çağırmaz.
// Bu XE alanı için giriş "Apple, 2" görüntüleyecektir.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apple";

Assert.AreEqual(" XE  Apple", indexEntry.GetFieldCode());

// Sayfa 3'e başka bir XE alanı ekleyin ve PageNumberReplacement özelliği için bir değer ayarlayın.
// Bu alanın bulunduğu sayfa numarası yerine bu değer gelecek,
// ve INDEX alanının CrossReferenceSeparator değeri onun önünde görünecektir.
// Bu XE alanı için giriş "Muz, bkz: Tropikal meyve" gösterecektir.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Banana";
indexEntry.PageNumberReplacement = "Tropical fruit";

Assert.AreEqual(" XE  Banana \\t \"Tropical fruit\"", indexEntry.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.CrossReferenceSeparator.docx");
```

### Ayrıca bakınız

* class [FieldXE](../)
* ad alanı [Aspose.Words.Fields](../../fieldxe/)
* toplantı [Aspose.Words](../../../)


