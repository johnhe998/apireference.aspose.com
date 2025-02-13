---
title: FindReplaceOptions.IgnoreFieldCodes
second_title: Référence de l'API Aspose.Words pour .NET
description: FindReplaceOptions propriété. Obtient ou définit une valeur booléenne indiquant soit dignorer le texte à lintérieur des codes de champ. La valeur par défaut estfaux .
type: docs
weight: 70
url: /fr/net/aspose.words.replacing/findreplaceoptions/ignorefieldcodes/
---
## FindReplaceOptions.IgnoreFieldCodes property

Obtient ou définit une valeur booléenne indiquant soit d'ignorer le texte à l'intérieur des codes de champ. La valeur par défaut est`faux` .

```csharp
public bool IgnoreFieldCodes { get; set; }
```

### Remarques

Cette option affecte uniquement les codes de champ (elle n'ignore pas les nœuds between FieldSeparator etFieldEnd).

Pour ignorer tout le champ, veuillez utiliser l'option correspondante[`IgnoreFields`](../ignorefields/).

### Exemples

Montre comment ignorer le texte à l'intérieur des codes de champ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("INCLUDETEXT", "Test IT!");

FindReplaceOptions options = new FindReplaceOptions {IgnoreFieldCodes = ignoreFieldCodes};

// Remplacez 'T' dans le document en ignorant ou non le texte à l'intérieur du code de champ.
doc.Range.Replace(new Regex("T"), "*", options);
Console.WriteLine(doc.GetText());

Assert.AreEqual(
    ignoreFieldCodes
        ? "\u0013INCLUDETEXT\u0014*est I*!\u0015"
        : "\u0013INCLUDE*EX*\u0014*est I*!\u0015", doc.GetText().Trim());
```

### Voir également

* class [FindReplaceOptions](../)
* espace de noms [Aspose.Words.Replacing](../../findreplaceoptions/)
* Assemblée [Aspose.Words](../../../)


