---
title: UserInformation.Address
second_title: Aspose.Words für .NET-API-Referenz
description: UserInformation eigendom. Ruft die Postanschrift des Benutzers ab oder legt sie fest.
type: docs
weight: 30
url: /de/net/aspose.words.fields/userinformation/address/
---
## UserInformation.Address property

Ruft die Postanschrift des Benutzers ab oder legt sie fest.

```csharp
public string Address { get; set; }
```

### Beispiele

Zeigt, wie Benutzerdetails festgelegt und mithilfe von Feldern angezeigt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie ein UserInformation-Objekt und legen Sie es als Datenquelle für Felder fest, die Benutzerinformationen anzeigen.
UserInformation userInformation = new UserInformation
{
    Name = "John Doe",
    Initials = "J. D.",
    Address = "123 Main Street"
};
doc.FieldOptions.CurrentUser = userInformation;

// Felder USERNAME, USERINITIALS und USERADDRESS einfügen, die Werte von anzeigen
// die entsprechenden Eigenschaften des oben erstellten UserInformation-Objekts. 
Assert.AreEqual(userInformation.Name, builder.InsertField(" USERNAME ").Result);
Assert.AreEqual(userInformation.Initials, builder.InsertField(" USERINITIALS ").Result);
Assert.AreEqual(userInformation.Address, builder.InsertField(" USERADDRESS ").Result);

// Das Feldoptionsobjekt hat auch einen statischen Standardbenutzer, auf den sich Felder aus allen Dokumenten beziehen können.
UserInformation.DefaultUser.Name = "Default User";
UserInformation.DefaultUser.Initials = "D. U.";
UserInformation.DefaultUser.Address = "One Microsoft Way";
doc.FieldOptions.CurrentUser = UserInformation.DefaultUser;

Assert.AreEqual("Default User", builder.InsertField(" USERNAME ").Result);
Assert.AreEqual("D. U.", builder.InsertField(" USERINITIALS ").Result);
Assert.AreEqual("One Microsoft Way", builder.InsertField(" USERADDRESS ").Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.CurrentUser.docx");
```

### Siehe auch

* class [UserInformation](../)
* namensraum [Aspose.Words.Fields](../../userinformation/)
* Montage [Aspose.Words](../../../)


