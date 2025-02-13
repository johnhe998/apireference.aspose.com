---
title: Field.DisplayResult
second_title: Aspose.Words for .NET API Referansı
description: Field mülk. Görüntülenen alan sonucunu temsil eden metni alır.
type: docs
weight: 10
url: /tr/net/aspose.words.fields/field/displayresult/
---
## Field.DisplayResult property

Görüntülenen alan sonucunu temsil eden metni alır.

```csharp
public string DisplayResult { get; }
```

### Notlar

[`UpdateListLabels`](../../../aspose.words/document/updatelistlabels/) the için doğru değeri elde etmek için yöntem çağrılmalıdır[`FieldListNum`](../../fieldlistnum/) ,[`FieldAutoNum`](../../fieldautonum/) ,[`FieldAutoNumOut`](../../fieldautonumout/) ve[`FieldAutoNumLgl`](../../fieldautonumlgl/) alanlar.

### Örnekler

Bir alanın belgede görüntülediği gerçek metnin nasıl alınacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This document was written by ");
FieldAuthor fieldAuthor = (FieldAuthor)builder.InsertField(FieldType.FieldAuthor, true);
fieldAuthor.AuthorName = "John Doe";

// Tam metnin ne olduğunu doğrulamak için DisplayResult özelliğini kullanabiliriz.
// bir alan belgedeki yerinde görüntülenecektir.
Assert.AreEqual(string.Empty, fieldAuthor.DisplayResult);

 // Alanlar gerçek zamanlı olarak doğru sonuç değerlerini korumaz.
// Alanlarımızın herhangi bir zamanda doğru sonuçlar gösterdiğinden emin olmak için,
// gibi bir kaydetme işleminden hemen önce bunları manuel olarak güncellememiz gerekiyor.
fieldAuthor.Update();

Assert.AreEqual("John Doe", fieldAuthor.DisplayResult);

doc.Save(ArtifactsDir + "Field.DisplayResult.docx");
```

### Ayrıca bakınız

* class [Field](../)
* ad alanı [Aspose.Words.Fields](../../field/)
* toplantı [Aspose.Words](../../../)


