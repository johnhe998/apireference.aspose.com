---
title: Class UserInformation
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fields.UserInformation classe. Spécifie des informations sur lutilisateur.
type: docs
weight: 2610
url: /fr/net/aspose.words.fields/userinformation/
---
## UserInformation class

Spécifie des informations sur l'utilisateur.

```csharp
public class UserInformation
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [UserInformation](userinformation/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| static [DefaultUser](../../aspose.words.fields/userinformation/defaultuser/) { get; } | Informations utilisateur par défaut. |
| [Address](../../aspose.words.fields/userinformation/address/) { get; set; } | Obtient ou définit l'adresse postale de l'utilisateur. |
| [Initials](../../aspose.words.fields/userinformation/initials/) { get; set; } | Obtient ou définit les initiales de l'utilisateur. |
| [Name](../../aspose.words.fields/userinformation/name/) { get; set; } | Obtient ou définit le nom de l'utilisateur. |

### Exemples

Montre comment définir les détails de l'utilisateur et les afficher à l'aide de champs.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crée un objet UserInformation et le définit comme source de données pour les champs qui affichent des informations sur l'utilisateur.
UserInformation userInformation = new UserInformation
{
    Name = "John Doe",
    Initials = "J. D.",
    Address = "123 Main Street"
};
doc.FieldOptions.CurrentUser = userInformation;

// Insérez les champs USERNAME, USERINITIALS et USERADDRESS, qui affichent les valeurs de
// les propriétés respectives de l'objet UserInformation que nous avons créé ci-dessus. 
Assert.AreEqual(userInformation.Name, builder.InsertField(" USERNAME ").Result);
Assert.AreEqual(userInformation.Initials, builder.InsertField(" USERINITIALS ").Result);
Assert.AreEqual(userInformation.Address, builder.InsertField(" USERADDRESS ").Result);

// L'objet d'options de champ a également un utilisateur statique par défaut auquel les champs de tous les documents peuvent se référer.
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

### Voir également

* espace de noms [Aspose.Words.Fields](../../aspose.words.fields/)
* Assemblée [Aspose.Words](../../)


