---
title: PlainTextDocument.BuiltInDocumentProperties
second_title: Référence de l'API Aspose.Words pour .NET
description: PlainTextDocument propriété. ObtientBuiltInDocumentProperties du document.
type: docs
weight: 20
url: /fr/net/aspose.words/plaintextdocument/builtindocumentproperties/
---
## PlainTextDocument.BuiltInDocumentProperties property

Obtient`BuiltInDocumentProperties` du document.

```csharp
public BuiltInDocumentProperties BuiltInDocumentProperties { get; }
```

### Exemples

Montre comment charger le contenu d'un document Microsoft Word en texte brut, puis accéder aux propriétés intégrées du document d'origine.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
doc.BuiltInDocumentProperties.Author = "John Doe";

doc.Save(ArtifactsDir + "PlainTextDocument.BuiltInProperties.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.BuiltInProperties.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
Assert.AreEqual("John Doe", plaintext.BuiltInDocumentProperties.Author);
```

### Voir également

* class [BuiltInDocumentProperties](../../../aspose.words.properties/builtindocumentproperties/)
* class [PlainTextDocument](../)
* espace de noms [Aspose.Words](../../plaintextdocument/)
* Assemblée [Aspose.Words](../../../)


