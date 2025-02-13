---
title: FieldIndex.RunSubentriesOnSameLine
second_title: Aspose.Words for .NET API Referansı
description: FieldIndex mülk. Alt girdilerin ana girdiyle aynı satırda çalıştırılıp çalıştırılmayacağını alır veya ayarlar.
type: docs
weight: 140
url: /tr/net/aspose.words.fields/fieldindex/runsubentriesonsameline/
---
## FieldIndex.RunSubentriesOnSameLine property

Alt girdilerin ana girdiyle aynı satırda çalıştırılıp çalıştırılmayacağını alır veya ayarlar.

```csharp
public bool RunSubentriesOnSameLine { get; set; }
```

### Örnekler

Bir INDEX alanındaki alt girdilerle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belgede bulunan her XE alanı için bir giriş görüntüleyecek bir INDEX alanı oluşturun.
// Her giriş, sol tarafta XE alanının Text özellik değerini gösterecek,
// ve sağdaki XE alanını içeren sayfanın numarası.
// INDEX girişi, "Metin" özelliğinde eşleşen değerlere sahip tüm XE alanlarını toplayacaktır.
// her XE alanı için bir giriş yapmak yerine tek bir girişe.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);
index.PageNumberSeparator = ", see page ";
index.Heading = "A";

// Değeri INDEX girişinin başlığı olan Text özelliğine sahip XE alanları.
// Bu değer, iki nokta üst üste ile ayrılmış iki dize segmenti içeriyorsa (INDEX girişi :) sınırlayıcıyı ele alır,
// ilk bölüm başlık ve ikinci bölüm alt başlık olacak.
// INDEX alanı önce girdileri alfabetik olarak gruplandırır, ardından aynı koda sahip birden fazla XE alanı varsa
// başlıklar, INDEX alanı onları bu başlıkların değerlerine göre alt gruplandıracaktır.
// Kaç defa olduğuna bağlı olarak birden fazla alt gruplama katmanı olabilir
// XE alanlarının Metin özellikleri bu şekilde segmentlere ayrılır.
 // Varsayılan olarak, bir INDEX alanı giriş grubu, bu gruptaki her alt başlık için yeni bir satır oluşturacaktır.
// Başlığı korumak için RunSubentriesOnSameLine bayrağını true olarak ayarlayabiliriz,
// ve grup için her alt başlık bunun yerine bir satırda olacak, bu da INDEX alanını daha kompakt hale getirecek.
index.RunSubentriesOnSameLine = runSubentriesOnTheSameLine;

if (runSubentriesOnTheSameLine)
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A \\r", index.GetFieldCode());
else
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A", index.GetFieldCode());

// Her biri yeni bir sayfada ve "Başlık 1" adlı aynı başlığa sahip iki XE alanı ekleyin,
// INDEX alanının bunları gruplamak için kullanacağı.
// RunSubentriesOnSameLine false ise, INDEX tablosu üç satır oluşturur:
// "Başlık 1" gruplandırma başlığı için bir satır ve her alt başlık için bir satır daha.
// RunSubentriesOnSameLine true ise, INDEX tablosu tek satırlık bir
// başlığı ve her alt başlığı kapsayan giriş.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 1";

Assert.AreEqual(" XE  \"Heading 1:Subheading 1\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 2";

doc.UpdateFields();
doc.Save(ArtifactsDir + $"Field.INDEX.XE.Subheading.docx");
```

### Ayrıca bakınız

* class [FieldIndex](../)
* ad alanı [Aspose.Words.Fields](../../fieldindex/)
* toplantı [Aspose.Words](../../../)


