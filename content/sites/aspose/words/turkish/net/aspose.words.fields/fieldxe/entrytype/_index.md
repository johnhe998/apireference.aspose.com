---
title: FieldXE.EntryType
second_title: Aspose.Words for .NET API Referansı
description: FieldXE mülk. Bir dizin girişi türü alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldxe/entrytype/
---
## FieldXE.EntryType property

Bir dizin girişi türü alır veya ayarlar.

```csharp
public string EntryType { get; set; }
```

### Örnekler

Bir INDEX alanının nasıl oluşturulacağını ve ardından onu girdilerle doldurmak için XE alanlarının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belgede bulunan her XE alanı için bir giriş görüntüleyecek bir INDEX alanı oluşturun.
// Her giriş, XE alanının Metin özellik değerini sol tarafta gösterecek
// ve sağda XE alanını içeren sayfa.
// XE alanları "Text" özelliğinde aynı değere sahipse,
// INDEX alanı bunları tek bir girişte gruplayacaktır.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// INDEX alanını yalnızca sınırlar içindeki XE alanlarını gösterecek şekilde yapılandırın
// "MainBookmark" adlı ve "EntryType" özellikleri "A" değerine sahip bir yer işaretinin.
// Hem INDEX hem de XE alanları için "EntryType" özelliği, dize değerinin yalnızca ilk karakterini kullanır.
index.BookmarkName = "MainBookmark";
index.EntryType = "A";

Assert.AreEqual(" INDEX  \\b MainBookmark \\f A", index.GetFieldCode());

// Yeni bir sayfada, yer imini değerle eşleşen bir adla başlatın
// INDEX alanının "Yer İşaretiAdı" özelliğinin.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MainBookmark");

// INDEX alanı, yer iminin içinde olduğu için bu girişi alacaktır,
// ve onun giriş tipi de INDEX alanının giriş tipiyle eşleşir.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 1";
indexEntry.EntryType = "A";

Assert.AreEqual(" XE  \"Index entry 1\" \\f A", indexEntry.GetFieldCode());

// Giriş türleri eşleşmediği için INDEX'te görünmeyecek bir XE alanı ekleyin.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 2";
indexEntry.EntryType = "B";

// Yer imini sonlandırın ve ardından bir XE alanı ekleyin.
// INDEX alanıyla aynı türdendir, ancak görünmeyecektir
// yer iminin sınırlarının dışında olduğu için.
builder.EndBookmark("MainBookmark");
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 3";
indexEntry.EntryType = "A";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Filtering.docx");
```

### Ayrıca bakınız

* class [FieldXE](../)
* ad alanı [Aspose.Words.Fields](../../fieldxe/)
* toplantı [Aspose.Words](../../../)


