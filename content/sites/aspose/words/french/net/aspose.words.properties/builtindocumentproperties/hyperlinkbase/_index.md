---
title: BuiltInDocumentProperties.HyperlinkBase
second_title: Référence de l'API Aspose.Words pour .NET
description: BuiltInDocumentProperties propriété. Spécifie la chaîne de base utilisée pour évaluer les hyperliens relatifs dans ce document.
type: docs
weight: 120
url: /fr/net/aspose.words.properties/builtindocumentproperties/hyperlinkbase/
---
## BuiltInDocumentProperties.HyperlinkBase property

Spécifie la chaîne de base utilisée pour évaluer les hyperliens relatifs dans ce document.

```csharp
public string HyperlinkBase { get; set; }
```

### Remarques

Aspose.Words n'utilise pas cette propriété.

### Exemples

Montre comment stocker la partie de base d'un lien hypertexte dans les propriétés du document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère un lien hypertexte relatif vers un document dans le système de fichiers local nommé "Document.docx".
// Cliquer sur le lien dans Microsoft Word ouvrira le document désigné, s'il est disponible.
builder.InsertHyperlink("Relative hyperlink", "Document.docx", false);

// Ce lien est relatif. S'il n'y a pas de "Document.docx" dans le même dossier
// comme le document qui contient ce lien, le lien sera rompu.
Assert.False(File.Exists(ArtifactsDir + "Document.docx"));
doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.BrokenLink.docx");

// Le document auquel nous essayons de créer un lien se trouve dans un répertoire différent de celui dans lequel nous prévoyons d'enregistrer le document.
// Nous pourrions réparer des liens comme celui-ci en mettant un nom de fichier absolu dans chacun d'eux. 
// Alternativement, nous pourrions fournir un lien de base que chaque lien hypertexte avec un nom de fichier relatif
// sera ajouté à son lien lorsque nous cliquons dessus. 
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;
properties.HyperlinkBase = MyDir;

Assert.True(File.Exists(properties.HyperlinkBase + ((FieldHyperlink)doc.Range.Fields[0]).Address));

doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.WorkingLink.docx");
```

### Voir également

* class [BuiltInDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../builtindocumentproperties/)
* Assemblée [Aspose.Words](../../../)


