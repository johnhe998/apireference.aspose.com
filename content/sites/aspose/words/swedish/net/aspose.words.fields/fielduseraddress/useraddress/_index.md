---
title: FieldUserAddress.UserAddress
second_title: Aspose.Words för .NET API Referens
description: FieldUserAddress fast egendom. Hämtar eller ställer in den aktuella användarens postadress.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fielduseraddress/useraddress/
---
## FieldUserAddress.UserAddress property

Hämtar eller ställer in den aktuella användarens postadress.

```csharp
public string UserAddress { get; set; }
```

### Exempel

Visar hur man använder fältet ANVÄNDARADRESS.

```csharp
Document doc = new Document();

// Skapa ett UserInformation-objekt och ställ in det som källa för användarinformation för alla fält som vi skapar.
UserInformation userInformation = new UserInformation();
userInformation.Address = "123 Main Street";
doc.FieldOptions.CurrentUser = userInformation;

// Skapa ett ANVÄNDARADRESS-fält för att visa den aktuella användarens adress,
// hämtat från UserInformation-objektet vi skapade ovan.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldUserAddress fieldUserAddress = (FieldUserAddress)builder.InsertField(FieldType.FieldUserAddress, true);
Assert.AreEqual(" USERADDRESS ", fieldUserAddress.GetFieldCode());
Assert.AreEqual("123 Main Street", fieldUserAddress.Result);

  // Vi kan ställa in den här egenskapen för att få vårt fält att åsidosätta värdet som för närvarande är lagrat i UserInformation-objektet.
fieldUserAddress.UserAddress = "456 North Road";
fieldUserAddress.Update();

Assert.AreEqual(" USERADDRESS  \"456 North Road\"", fieldUserAddress.GetFieldCode());
Assert.AreEqual("456 North Road", fieldUserAddress.Result);

// Detta påverkar inte värdet i UserInformation-objektet.
Assert.AreEqual("123 Main Street", doc.FieldOptions.CurrentUser.Address);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.USERADDRESS.docx");
```

### Se även

* class [FieldUserAddress](../)
* namnutrymme [Aspose.Words.Fields](../../fielduseraddress/)
* hopsättning [Aspose.Words](../../../)


