---
title: Enum ContentDisposition
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.ContentDisposition énumération. Énumère différentes manières de présenter le document sur le navigateur client.
type: docs
weight: 330
url: /fr/net/aspose.words/contentdisposition/
---
## ContentDisposition enumeration

Énumère différentes manières de présenter le document sur le navigateur client.

```csharp
public enum ContentDisposition
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Attachment | `0` | Envoyez le document au navigateur et présentez une option pour enregistrer le document sur le disque ou l'ouvrir dans l'application associée à l'extension du document. |
| Inline | `1` | Envoie le document au navigateur et présente une option pour enregistrer le document sur le disque ou l'ouvrir dans le navigateur. |

### Remarques

Notez que le comportement réel sur le navigateur client peut être affecté par la configuration de sécurité du navigateur.

### Exemples

Montre comment effectuer un publipostage, puis enregistrer le document dans le navigateur client.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD FullName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Company ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Address ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

doc.MailMerge.Execute(new string[] { "FullName", "Company", "Address", "City" },
    new object[] { "James Bond", "MI5 Headquarters", "Milbank", "London" });

// Envoie le document au navigateur client.
Assert.That(() => doc.Save(response, "Artifacts/MailMerge.ExecuteArray.docx", ContentDisposition.Inline, null),
    Throws.TypeOf<ArgumentNullException>()); //Lancé car HttpResponse est nul dans le test.

// Nous devrons fermer cette réponse manuellement pour nous assurer de ne pas ajouter de contenu superflu au document après l'enregistrement.
Assert.That(() => response.End(), Throws.TypeOf<NullReferenceException>());
```

### Voir également

* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


