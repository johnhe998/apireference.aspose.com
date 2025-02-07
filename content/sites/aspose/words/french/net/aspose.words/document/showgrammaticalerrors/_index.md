---
title: Document.ShowGrammaticalErrors
second_title: Référence de l'API Aspose.Words pour .NET
description: Document propriété. Spécifie sil faut afficher les erreurs de grammaire dans ce document.
type: docs
weight: 370
url: /fr/net/aspose.words/document/showgrammaticalerrors/
---
## Document.ShowGrammaticalErrors property

Spécifie s'il faut afficher les erreurs de grammaire dans ce document.

```csharp
public bool ShowGrammaticalErrors { get; set; }
```

### Exemples

Montre comment afficher/masquer les erreurs dans le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère deux phrases avec des fautes qui seraient relevées
// par les vérificateurs d'orthographe et de grammaire de Microsoft Word.
builder.Writeln("There is a speling error in this sentence.");
builder.Writeln("Their is a grammatical error in this sentence.");

// Si ces options sont activées, les fautes d'orthographe seront soulignées
// dans le document de sortie par une ligne rouge irrégulière, et une double ligne bleue mettra en évidence les fautes de grammaire.
doc.ShowGrammaticalErrors = showErrors;
doc.ShowSpellingErrors = showErrors;

doc.Save(ArtifactsDir + "Document.SpellingAndGrammarErrors.docx");
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


