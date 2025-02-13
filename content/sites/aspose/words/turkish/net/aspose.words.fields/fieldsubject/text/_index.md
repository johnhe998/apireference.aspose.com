---
title: FieldSubject.Text
second_title: Aspose.Words for .NET API Referansı
description: FieldSubject mülk. Konunun metnini alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldsubject/text/
---
## FieldSubject.Text property

Konunun metnini alır veya ayarlar.

```csharp
public string Text { get; set; }
```

### Örnekler

KONU alanının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();

// Belgenin yerleşik "Konu" özelliği için bir değer ayarlayın.
doc.BuiltInDocumentProperties.Subject = "My subject";

// Bu yerleşik özelliğin değerini görüntülemek için bir KONU alanı oluşturun.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldSubject field = (FieldSubject)builder.InsertField(FieldType.FieldSubject, true);
field.Update();

Assert.AreEqual(" SUBJECT ", field.GetFieldCode());
Assert.AreEqual("My subject", field.Result);

// SUBJECT alanının Text özellik değerini verip güncellersek alan
// "Konu" yerleşik özelliğinin geçerli değerinin üzerine Metin özelliğinin değeriyle yaz,
// ve ardından yeni değeri görüntüleyin.
field.Text = "My new subject";
field.Update();

Assert.AreEqual(" SUBJECT  \"My new subject\"", field.GetFieldCode());
Assert.AreEqual("My new subject", field.Result);

Assert.AreEqual("My new subject", doc.BuiltInDocumentProperties.Subject);

doc.Save(ArtifactsDir + "Field.SUBJECT.docx");
```

### Ayrıca bakınız

* class [FieldSubject](../)
* ad alanı [Aspose.Words.Fields](../../fieldsubject/)
* toplantı [Aspose.Words](../../../)


