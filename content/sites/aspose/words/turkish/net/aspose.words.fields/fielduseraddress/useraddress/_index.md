---
title: FieldUserAddress.UserAddress
second_title: Aspose.Words for .NET API Referansı
description: FieldUserAddress mülk. Geçerli kullanıcının posta adresini alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fielduseraddress/useraddress/
---
## FieldUserAddress.UserAddress property

Geçerli kullanıcının posta adresini alır veya ayarlar.

```csharp
public string UserAddress { get; set; }
```

### Örnekler

USERADDRESS alanının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();

// Bir UserInformation nesnesi oluşturun ve oluşturduğumuz tüm alanlar için kullanıcı bilgilerinin kaynağı olarak ayarlayın.
UserInformation userInformation = new UserInformation();
userInformation.Address = "123 Main Street";
doc.FieldOptions.CurrentUser = userInformation;

// Mevcut kullanıcının adresini görüntülemek için bir USERADDRESS alanı oluşturun,
// yukarıda oluşturduğumuz UserInformation nesnesinden alınmıştır.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldUserAddress fieldUserAddress = (FieldUserAddress)builder.InsertField(FieldType.FieldUserAddress, true);
Assert.AreEqual(" USERADDRESS ", fieldUserAddress.GetFieldCode());
Assert.AreEqual("123 Main Street", fieldUserAddress.Result);

 // Bu özelliği, alanımızın UserInformation nesnesinde şu anda depolanan değeri geçersiz kılacak şekilde ayarlayabiliriz.
fieldUserAddress.UserAddress = "456 North Road";
fieldUserAddress.Update();

Assert.AreEqual(" USERADDRESS  \"456 North Road\"", fieldUserAddress.GetFieldCode());
Assert.AreEqual("456 North Road", fieldUserAddress.Result);

// Bu, UserInformation nesnesindeki değeri etkilemez.
Assert.AreEqual("123 Main Street", doc.FieldOptions.CurrentUser.Address);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.USERADDRESS.docx");
```

### Ayrıca bakınız

* class [FieldUserAddress](../)
* ad alanı [Aspose.Words.Fields](../../fielduseraddress/)
* toplantı [Aspose.Words](../../../)


