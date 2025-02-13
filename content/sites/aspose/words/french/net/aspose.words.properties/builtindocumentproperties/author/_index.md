---
title: BuiltInDocumentProperties.Author
second_title: Référence de l'API Aspose.Words pour .NET
description: BuiltInDocumentProperties propriété. Obtient ou définit le nom de lauteur du document.
type: docs
weight: 10
url: /fr/net/aspose.words.properties/builtindocumentproperties/author/
---
## BuiltInDocumentProperties.Author property

Obtient ou définit le nom de l'auteur du document.

```csharp
public string Author { get; set; }
```

### Exemples

Montre comment utiliser les propriétés de document intégrées dans la catégorie "Description".

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

// Vous trouverez ci-dessous quatre propriétés de document intégrées qui ont des champs qui peuvent afficher leurs valeurs dans le corps du document.
// 1 - Propriété "Auteur", que l'on peut afficher à l'aide d'un champ AUTEUR :
properties.Author = "John Doe";
builder.Write("Author:\t");
builder.InsertField(FieldType.FieldAuthor, true);

// 2 - Propriété "Title", que l'on peut afficher à l'aide d'un champ TITLE :
properties.Title = "John's Document";
builder.Write("\nDoc title:\t");
builder.InsertField(FieldType.FieldTitle, true);

// 3 - Propriété "Subject", que l'on peut afficher à l'aide d'un champ SUBJECT :
properties.Subject = "My subject";
builder.Write("\nSubject:\t");
builder.InsertField(FieldType.FieldSubject, true);

// 4 - Propriété "Comments", que l'on peut afficher à l'aide d'un champ COMMENTS :
properties.Comments = $"This is {properties.Author}'s document about {properties.Subject}";
builder.Write("\nComments:\t\"");
builder.InsertField(FieldType.FieldComments, true);
builder.Write("\"");

// La propriété intégrée "Catégorie" n'a pas de champ pouvant afficher sa valeur.
properties.Category = "My category";

// Nous pouvons définir plusieurs mots clés pour un document en séparant la valeur de chaîne de la propriété "Keywords" par des points-virgules.
properties.Keywords = "Tag 1; Tag 2; Tag 3";

// Nous pouvons faire un clic droit sur ce document dans l'Explorateur Windows et trouver ces propriétés dans "Propriétés" -> "Détails".
// La propriété intégrée "Auteur" est dans le groupe "Origine", et les autres sont dans le groupe "Description".
doc.Save(ArtifactsDir + "DocumentProperties.Description.docx");
```

### Voir également

* class [BuiltInDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../builtindocumentproperties/)
* Assemblée [Aspose.Words](../../../)


