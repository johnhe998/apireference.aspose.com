---
title: FieldUserInitials.UserInitials
second_title: Aspose.Words für .NET-API-Referenz
description: FieldUserInitials eigendom. Ruft die Initialen des aktuellen Benutzers ab oder legt sie fest.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fielduserinitials/userinitials/
---
## FieldUserInitials.UserInitials property

Ruft die Initialen des aktuellen Benutzers ab oder legt sie fest.

```csharp
public string UserInitials { get; set; }
```

### Beispiele

Zeigt, wie das Feld USERINITIALS verwendet wird.

```csharp
Document doc = new Document();

// Erstellen Sie ein UserInformation-Objekt und legen Sie es als Quelle der Benutzerinformationen für alle von uns erstellten Felder fest.
UserInformation userInformation = new UserInformation();
userInformation.Initials = "J. D.";
doc.FieldOptions.CurrentUser = userInformation;

// Erstellen Sie ein USERINITIALS-Feld, um die Initialen des aktuellen Benutzers anzuzeigen,
// entnommen aus dem oben erstellten UserInformation-Objekt.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldUserInitials fieldUserInitials = (FieldUserInitials)builder.InsertField(FieldType.FieldUserInitials, true);
Assert.AreEqual(userInformation.Initials, fieldUserInitials.Result);

Assert.AreEqual(" USERINITIALS ", fieldUserInitials.GetFieldCode());
Assert.AreEqual("J. D.", fieldUserInitials.Result);

 // Wir können diese Eigenschaft setzen, damit unser Feld den aktuell im UserInformation-Objekt gespeicherten Wert überschreibt.
fieldUserInitials.UserInitials = "J. C.";
fieldUserInitials.Update();

Assert.AreEqual(" USERINITIALS  \"J. C.\"", fieldUserInitials.GetFieldCode());
Assert.AreEqual("J. C.", fieldUserInitials.Result);

// Dies wirkt sich nicht auf den Wert im UserInformation-Objekt aus.
Assert.AreEqual("J. D.", doc.FieldOptions.CurrentUser.Initials);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.USERINITIALS.docx");
```

### Siehe auch

* class [FieldUserInitials](../)
* namensraum [Aspose.Words.Fields](../../fielduserinitials/)
* Montage [Aspose.Words](../../../)


