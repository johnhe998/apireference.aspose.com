---
title: FieldInclude.BookmarkName
second_title: Aspose.Words for .NET API Referansı
description: FieldInclude mülk. Dahil edilecek yer iminin adını alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldinclude/bookmarkname/
---
## FieldInclude.BookmarkName property

Dahil edilecek yer iminin adını alır veya ayarlar.

```csharp
public string BookmarkName { get; set; }
```

### Örnekler

INCLUDE alanının nasıl oluşturulacağını ve özelliklerinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Yerel dosya sisteminde başka bir belgenin bir bölümünü içe aktarmak için bir INCLUDE alanını kullanabiliriz.
// Bu alanla referans verdiğimiz diğer belgedeki yer imi, içe aktarılan bu kısmı içerir.
FieldInclude field = (FieldInclude)builder.InsertField(FieldType.FieldInclude, true);
field.SourceFullName = MyDir + "Bookmarks.docx";
field.BookmarkName = "MyBookmark1";
field.LockFields = false;
field.TextConverter = "Microsoft Word";

Assert.True(Regex.Match(field.GetFieldCode(), " INCLUDE .* MyBookmark1 \\\\c \"Microsoft Word\"").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INCLUDE.docx");
```

### Ayrıca bakınız

* class [FieldInclude](../)
* ad alanı [Aspose.Words.Fields](../../fieldinclude/)
* toplantı [Aspose.Words](../../../)


