---
title: MailMergeSettings.HeaderSource
second_title: Référence de l'API Aspose.Words pour .NET
description: MailMergeSettings propriété. Spécifie le chemin daccès à la source de lentête de publipostage. La valeur par défaut est une chaîne vide.
type: docs
weight: 100
url: /fr/net/aspose.words.settings/mailmergesettings/headersource/
---
## MailMergeSettings.HeaderSource property

Spécifie le chemin d'accès à la source de l'en-tête de publipostage. La valeur par défaut est une chaîne vide.

```csharp
public string HeaderSource { get; set; }
```

### Exemples

Montre comment construire une source de données pour un publipostage à partir d'une source d'en-tête et d'une source de données.

```csharp
// Crée un fichier d'en-tête de fusion d'étiquette de publipostage, qui consistera en un tableau avec une ligne.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();
builder.InsertCell();
builder.Write("FirstName");
builder.InsertCell();
builder.Write("LastName");
builder.EndTable();

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.Header.docx");

// Crée un fichier de données de fusion d'étiquettes postales composé d'un tableau à une ligne
// et le même nombre de colonnes que le tableau du document d'en-tête. 
doc = new Document();
builder = new DocumentBuilder(doc);

builder.StartTable();
builder.InsertCell();
builder.Write("John");
builder.InsertCell();
builder.Write("Doe");
builder.EndTable();

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.Data.docx");

// Crée un document de destination de fusion avec MERGEFIELDS avec des noms qui
// correspond aux noms de colonne dans la table du fichier d'en-tête de fusion.
doc = new Document();
builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");

MailMergeSettings settings = doc.MailMergeSettings;

// Construire une source de données pour notre publipostage en spécifiant deux noms de fichier de document.
// La source d'en-tête nommera les colonnes de la table de la source de données.
settings.HeaderSource = ArtifactsDir + "MailMerge.MailingLabelMerge.Header.docx";

// La source de données fournira des lignes de données pour toutes les colonnes de la table de document d'en-tête.
settings.DataSource = ArtifactsDir + "MailMerge.MailingLabelMerge.Data.docx";

// Configurez un publipostage de type étiquette de publipostage, que Microsoft Word exécutera
// dès que nous l'utilisons pour charger le document de sortie.
settings.Query = "SELECT * FROM " + settings.DataSource;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.DataType = MailMergeDataType.TextFile;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.docx");
```

### Voir également

* class [MailMergeSettings](../)
* espace de noms [Aspose.Words.Settings](../../mailmergesettings/)
* Assemblée [Aspose.Words](../../../)


