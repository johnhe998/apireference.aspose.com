---
title: Class UserInformation
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Fields.UserInformation klas. Gibt Informationen über den Benutzer an.
type: docs
weight: 2610
url: /de/net/aspose.words.fields/userinformation/
---
## UserInformation class

Gibt Informationen über den Benutzer an.

```csharp
public class UserInformation
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [UserInformation](userinformation/)() | Default_Constructor |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| static [DefaultUser](../../aspose.words.fields/userinformation/defaultuser/) { get; } | Standardbenutzerinformationen. |
| [Address](../../aspose.words.fields/userinformation/address/) { get; set; } | Ruft die Postanschrift des Benutzers ab oder legt sie fest. |
| [Initials](../../aspose.words.fields/userinformation/initials/) { get; set; } | Ruft die Initialen des Benutzers ab oder legt sie fest. |
| [Name](../../aspose.words.fields/userinformation/name/) { get; set; } | Ruft den Namen des Benutzers ab oder legt ihn fest. |

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

* namensraum [Aspose.Words.Fields](../../aspose.words.fields/)
* Montage [Aspose.Words](../../)


