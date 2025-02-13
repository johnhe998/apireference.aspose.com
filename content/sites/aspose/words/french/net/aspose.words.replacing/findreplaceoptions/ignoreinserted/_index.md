---
title: FindReplaceOptions.IgnoreInserted
second_title: Référence de l'API Aspose.Words pour .NET
description: FindReplaceOptions propriété. Obtient ou définit une valeur booléenne indiquant soit dignorer le texte à lintérieur des révisions dinsertion. La valeur par défaut estfaux .
type: docs
weight: 100
url: /fr/net/aspose.words.replacing/findreplaceoptions/ignoreinserted/
---
## FindReplaceOptions.IgnoreInserted property

Obtient ou définit une valeur booléenne indiquant soit d'ignorer le texte à l'intérieur des révisions d'insertion. La valeur par défaut est`faux` .

```csharp
public bool IgnoreInserted { get; set; }
```

### Exemples

Montre comment inclure ou ignorer du texte dans les révisions d'insertion lors d'une opération de recherche et de remplacement.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

// Démarre le suivi des révisions et insère un paragraphe. Ce paragraphe sera une révision d'insertion.
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("Hello again!");
doc.StopTrackRevisions();

Assert.True(doc.FirstSection.Body.Paragraphs[1].IsInsertRevision);

// Nous pouvons utiliser un objet "FindReplaceOptions" pour modifier le processus de recherche et de remplacement.
FindReplaceOptions options = new FindReplaceOptions();

// Définissez le drapeau "IgnoreInserted" sur "true" pour obtenir la recherche et le remplacement
// opération pour ignorer les paragraphes qui sont des révisions d'insertion.
// Définissez le drapeau "IgnoreInserted" sur "false" pour obtenir la recherche et le remplacement
// opération pour rechercher également du texte à l'intérieur des révisions d'insertion.
options.IgnoreInserted = ignoreTextInsideInsertRevisions;

doc.Range.Replace("Hello", "Greetings", options);

Assert.AreEqual(
    ignoreTextInsideInsertRevisions
        ? "Greetings world!\rHello again!"
        : "Greetings world!\rGreetings again!", doc.GetText().Trim());
```

### Voir également

* class [FindReplaceOptions](../)
* espace de noms [Aspose.Words.Replacing](../../findreplaceoptions/)
* Assemblée [Aspose.Words](../../../)


