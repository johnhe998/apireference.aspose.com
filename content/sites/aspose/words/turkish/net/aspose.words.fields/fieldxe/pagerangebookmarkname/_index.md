---
title: FieldXE.PageRangeBookmarkName
second_title: Aspose.Words for .NET API Referansı
description: FieldXE mülk. Girdinin sayfa numarası olarak eklenen bir sayfa aralığını işaretleyen yer iminin adını alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.fields/fieldxe/pagerangebookmarkname/
---
## FieldXE.PageRangeBookmarkName property

Girdinin sayfa numarası olarak eklenen bir sayfa aralığını işaretleyen yer iminin adını alır veya ayarlar.

```csharp
public string PageRangeBookmarkName { get; set; }
```

### Örnekler

Bir INDEX alanı girişi için sayfa aralığı olarak bir yer iminin yayılmış sayfalarının nasıl belirtileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belgede bulunan her XE alanı için bir giriş görüntüleyecek bir INDEX alanı oluşturun.
// Her giriş, sol tarafta XE alanının Text özellik değerini gösterecek,
// ve sağdaki XE alanını içeren sayfanın numarası.
// INDEX girişi, "Metin" özelliğinde eşleşen değerlere sahip tüm XE alanlarını toplayacaktır.
// her XE alanı için bir giriş yapmak yerine tek bir girişe.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Sayfa aralıklarını gösteren INDEX girişleri için bir ayırıcı dize belirtebiliriz
// ilk sayfanın numarası ile son sayfanın numarası arasında görünecek.
index.PageNumberSeparator = ", on page(s) ";
index.PageRangeSeparator = " to ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\g \" to \"", index.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "My entry";

// Bir XE alanı, PageRangeBookmarkName özelliğini kullanarak bir yer işaretini adlandırırsa,
// INDEX girişi, yer iminin kapsadığı sayfa aralığını gösterecek
// XE alanını içeren sayfanın numarası yerine.
indexEntry.PageRangeBookmarkName = "MyBookmark";

Assert.AreEqual(" XE  \"My entry\" \\r MyBookmark", indexEntry.GetFieldCode());
Assert.AreEqual("MyBookmark", indexEntry.PageRangeBookmarkName);

// 3. sayfada başlayan ve 5. sayfada biten bir yer imi ekleyin.
// Bu yer işaretine başvuran XE alanı için INDEX girişi bu sayfa aralığını görüntüleyecektir.
// Tablomuzda, INDEX girişi "Girişim, sayfa(lar)da 3 ila 5" görüntüleyecektir.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MyBookmark");
builder.Write("Start of MyBookmark");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.Write("End of MyBookmark");
builder.EndBookmark("MyBookmark");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageRangeBookmark.docx");
```

### Ayrıca bakınız

* class [FieldXE](../)
* ad alanı [Aspose.Words.Fields](../../fieldxe/)
* toplantı [Aspose.Words](../../../)


