---
title: FieldFileSize.IsInMegabytes
second_title: Aspose.Words for .NET API Referansı
description: FieldFileSize mülk. Dosya boyutunun megabayt cinsinden görüntülenip görüntülenmeyeceğini ayarlar.
type: docs
weight: 30
url: /tr/net/aspose.words.fields/fieldfilesize/isinmegabytes/
---
## FieldFileSize.IsInMegabytes property

Dosya boyutunun megabayt cinsinden görüntülenip görüntülenmeyeceğini ayarlar.

```csharp
public bool IsInMegabytes { get; set; }
```

### Örnekler

DOSYA BOYUTU alanına sahip bir belgenin dosya boyutunun nasıl görüntüleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(18105, doc.BuiltInDocumentProperties.Bytes);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.InsertParagraph();

// Aşağıda üç farklı ölçü birimi var
// FILESIZE alanlarının belgenin dosya boyutunu gösterebileceği alanlar.
// 1 - Bayt:
FieldFileSize field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.Update();

Assert.AreEqual(" FILESIZE ", field.GetFieldCode());
Assert.AreEqual("18105", field.Result);

// 2 - Kilobayt:
builder.InsertParagraph();
field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.IsInKilobytes = true;
field.Update();

Assert.AreEqual(" FILESIZE  \\k", field.GetFieldCode());
Assert.AreEqual("18", field.Result);

// 3 - Megabayt:
builder.InsertParagraph();
field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.IsInMegabytes = true;
field.Update();

Assert.AreEqual(" FILESIZE  \\m", field.GetFieldCode());
Assert.AreEqual("0", field.Result);

// Microsoft Word'de düzenleme yaparken bu alanların değerlerini güncellemek için,
// önce değişiklikleri kaydetmeli, ardından bu alanları manuel olarak güncellemeliyiz.
doc.Save(ArtifactsDir + "Field.FILESIZE.docx");
```

### Ayrıca bakınız

* class [FieldFileSize](../)
* ad alanı [Aspose.Words.Fields](../../fieldfilesize/)
* toplantı [Aspose.Words](../../../)


