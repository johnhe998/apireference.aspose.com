---
title: FieldUserName.UserName
second_title: Aspose.Words for .NET API Referansı
description: FieldUserName mülk. Geçerli kullanıcının adını alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldusername/username/
---
## FieldUserName.UserName property

Geçerli kullanıcının adını alır veya ayarlar.

```csharp
public string UserName { get; set; }
```

### Örnekler

KULLANICI ADI alanının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();

// Bir UserInformation nesnesi oluşturun ve oluşturduğumuz tüm alanlar için kullanıcı bilgilerinin kaynağı olarak ayarlayın.
UserInformation userInformation = new UserInformation();
userInformation.Name = "John Doe";
doc.FieldOptions.CurrentUser = userInformation;

DocumentBuilder builder = new DocumentBuilder(doc);

// Mevcut kullanıcının adını görüntülemek için bir USERNAME alanı oluşturun,
// yukarıda oluşturduğumuz UserInformation nesnesinden alınmıştır.
FieldUserName fieldUserName = (FieldUserName)builder.InsertField(FieldType.FieldUserName, true);
Assert.AreEqual(userInformation.Name, fieldUserName.Result);

Assert.AreEqual(" USERNAME ", fieldUserName.GetFieldCode());
Assert.AreEqual("John Doe", fieldUserName.Result);

 // Bu özelliği, alanımızın UserInformation nesnesinde şu anda depolanan değeri geçersiz kılacak şekilde ayarlayabiliriz.
fieldUserName.UserName = "Jane Doe";
fieldUserName.Update();

Assert.AreEqual(" USERNAME  \"Jane Doe\"", fieldUserName.GetFieldCode());
Assert.AreEqual("Jane Doe", fieldUserName.Result);

// Bu, UserInformation nesnesindeki değeri etkilemez.
Assert.AreEqual("John Doe", doc.FieldOptions.CurrentUser.Name);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.USERNAME.docx");
```

### Ayrıca bakınız

* class [FieldUserName](../)
* ad alanı [Aspose.Words.Fields](../../fieldusername/)
* toplantı [Aspose.Words](../../../)


