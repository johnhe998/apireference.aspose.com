---
title: FieldIndex.PageNumberListSeparator
second_title: Aspose.Words for .NET API Referansı
description: FieldIndex mülk. Bir sayfa numarası listesindeki iki sayfa numarasını ayırmak için kullanılan karakter dizisini alır veya ayarlar.
type: docs
weight: 110
url: /tr/net/aspose.words.fields/fieldindex/pagenumberlistseparator/
---
## FieldIndex.PageNumberListSeparator property

Bir sayfa numarası listesindeki iki sayfa numarasını ayırmak için kullanılan karakter dizisini alır veya ayarlar.

```csharp
public string PageNumberListSeparator { get; set; }
```

### Örnekler

Bir INDEX alanında sayfa numarası ayırıcısının nasıl düzenleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belgede bulunan her XE alanı için bir giriş görüntüleyecek bir INDEX alanı oluşturun.
// Her giriş, sol tarafta XE alanının Text özellik değerini gösterecek,
// ve sağdaki XE alanını içeren sayfanın numarası.
// INDEX girişi, "Metin" özelliğinde eşleşen değerlere sahip XE alanlarını gruplayacaktır
// her XE alanı için bir giriş yapmak yerine tek bir girişe.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// INDEX alanımızda bir grup XE alanı için giriş varsa,
// bu giriş, bu gruba ait bir XE alanı içeren her sayfanın numarasını görüntüler.
// Bu sayfa numaralarının görünümünü özelleştirmek için özel ayırıcılar ayarlayabiliriz.
index.PageNumberSeparator = ", on page(s) ";
index.PageNumberListSeparator = " & ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\l \" & \"", index.GetFieldCode());
Assert.True(index.HasPageNumberSeparator);

// Bu XE alanlarını ekledikten sonra, INDEX alanında "İlk giriş, sayfa(lar) 2 & 3 & 4" görüntülenecektir.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

Assert.AreEqual(" XE  \"First entry\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageNumberList.docx");
```

### Ayrıca bakınız

* class [FieldIndex](../)
* ad alanı [Aspose.Words.Fields](../../fieldindex/)
* toplantı [Aspose.Words](../../../)


