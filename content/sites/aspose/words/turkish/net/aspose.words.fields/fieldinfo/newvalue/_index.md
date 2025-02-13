---
title: FieldInfo.NewValue
second_title: Aspose.Words for .NET API Referansı
description: FieldInfo mülk. Özelliği güncelleyen isteğe bağlı bir değer alır veya ayarlar.
type: docs
weight: 30
url: /tr/net/aspose.words.fields/fieldinfo/newvalue/
---
## FieldInfo.NewValue property

Özelliği güncelleyen isteğe bağlı bir değer alır veya ayarlar.

```csharp
public string NewValue { get; set; }
```

### Örnekler

BİLGİ alanlarıyla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "Yorumlar" yerleşik özelliği için bir değer belirleyin ve ardından bu özelliğin değerini görüntülemek için bir INFO alanı ekleyin.
doc.BuiltInDocumentProperties.Comments = "My comment";
FieldInfo field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.Update();

Assert.AreEqual(" INFO  Comments", field.GetFieldCode());
Assert.AreEqual("My comment", field.Result);

builder.Writeln();

// Alanın NewValue özelliği için bir değer belirleme ve güncelleme
// alan ayrıca yeni değeri karşılık gelen yerleşik özelliğin üzerine yazacaktır.
field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.NewValue = "New comment";
field.Update();

Assert.AreEqual(" INFO  Comments \"New comment\"", field.GetFieldCode());
Assert.AreEqual("New comment", field.Result);
Assert.AreEqual("New comment", doc.BuiltInDocumentProperties.Comments);

doc.Save(ArtifactsDir + "Field.INFO.docx");
```

### Ayrıca bakınız

* class [FieldInfo](../)
* ad alanı [Aspose.Words.Fields](../../fieldinfo/)
* toplantı [Aspose.Words](../../../)


