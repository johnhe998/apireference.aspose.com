---
title: FieldUserAddress.UserAddress
second_title: Aspose.Words für .NET-API-Referenz
description: FieldUserAddress eigendom. Ruft die Postanschrift des aktuellen Benutzers ab oder legt sie fest.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fielduseraddress/useraddress/
---
## FieldUserAddress.UserAddress property

Ruft die Postanschrift des aktuellen Benutzers ab oder legt sie fest.

```csharp
public string UserAddress { get; set; }
```

### Beispiele

Zeigt, wie das Feld USERADDRESS verwendet wird.

```csharp
Document doc = new Document();

// Erstellen Sie ein UserInformation-Objekt und legen Sie es als Quelle der Benutzerinformationen für alle von uns erstellten Felder fest.
UserInformation userInformation = new UserInformation();
userInformation.Address = "123 Main Street";
doc.FieldOptions.CurrentUser = userInformation;

// Erstellen Sie ein USERADDRESS-Feld, um die Adresse des aktuellen Benutzers anzuzeigen,
// entnommen aus dem oben erstellten UserInformation-Objekt.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldUserAddress fieldUserAddress = (FieldUserAddress)builder.InsertField(FieldType.FieldUserAddress, true);
Assert.AreEqual(" USERADDRESS ", fieldUserAddress.GetFieldCode());
Assert.AreEqual("123 Main Street", fieldUserAddress.Result);

 // Wir können diese Eigenschaft setzen, damit unser Feld den aktuell im UserInformation-Objekt gespeicherten Wert überschreibt.
fieldUserAddress.UserAddress = "456 North Road";
fieldUserAddress.Update();

Assert.AreEqual(" USERADDRESS  \"456 North Road\"", fieldUserAddress.GetFieldCode());
Assert.AreEqual("456 North Road", fieldUserAddress.Result);

// Dies wirkt sich nicht auf den Wert im UserInformation-Objekt aus.
Assert.AreEqual("123 Main Street", doc.FieldOptions.CurrentUser.Address);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.USERADDRESS.docx");
```

### Siehe auch

* class [FieldUserAddress](../)
* namensraum [Aspose.Words.Fields](../../fielduseraddress/)
* Montage [Aspose.Words](../../../)


