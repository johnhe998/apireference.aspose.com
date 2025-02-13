---
title: FieldComments.Text
second_title: Aspose.Words for .NET API Referansı
description: FieldComments mülk. Yorumların metnini alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldcomments/text/
---
## FieldComments.Text property

Yorumların metnini alır veya ayarlar.

```csharp
public string Text { get; set; }
```

### Örnekler

YORUMLAR alanının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belgenin yerleşik "Yorumlar" özelliği için bir değer ayarlayın.
doc.BuiltInDocumentProperties.Comments = "My comment.";

// Yerleşik özelliğin değerini görüntülemek için bir YORUMLAR alanı oluşturun.
FieldComments field = (FieldComments)builder.InsertField(FieldType.FieldComments, true);
field.Update();

Assert.AreEqual(" COMMENTS ", field.GetFieldCode());
Assert.AreEqual("My comment.", field.Result);

// YORUMLAR alanına Text özellik değerini verip güncellersek alan
// "Yorumlar" yerleşik özelliğinin geçerli değerinin üzerine Metin özelliğinin değeriyle yaz,
// ve ardından yeni değeri görüntüleyin.
field.Text = "My overriding comment.";
field.Update();

Assert.AreEqual(" COMMENTS  \"My overriding comment.\"", field.GetFieldCode());
Assert.AreEqual("My overriding comment.", field.Result);

doc.Save(ArtifactsDir + "Field.COMMENTS.docx");
```

### Ayrıca bakınız

* class [FieldComments](../)
* ad alanı [Aspose.Words.Fields](../../fieldcomments/)
* toplantı [Aspose.Words](../../../)


