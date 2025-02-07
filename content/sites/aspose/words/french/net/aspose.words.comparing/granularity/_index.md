---
title: Enum Granularity
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Comparing.Granularity énumération. Spécifie la granularité des modifications à suivre lors de la comparaison de deux documents.
type: docs
weight: 280
url: /fr/net/aspose.words.comparing/granularity/
---
## Granularity enumeration

Spécifie la granularité des modifications à suivre lors de la comparaison de deux documents.

```csharp
public enum Granularity
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| CharLevel | `0` |  |
| WordLevel | `1` |  |

### Exemples

Affiche pour spécifier une granularité lors de la comparaison de documents.

```csharp
Document docA = new Document();
DocumentBuilder builderA = new DocumentBuilder(docA);
builderA.Writeln("Alpha Lorem ipsum dolor sit amet, consectetur adipiscing elit");

Document docB = new Document();
DocumentBuilder builderB = new DocumentBuilder(docB);
builderB.Writeln("Lorems ipsum dolor sit amet consectetur - \"adipiscing\" elit");

// Spécifiez si les modifications sont suivies
// par caractère ('Granularity.CharLevel'), ou par mot ('Granularity.WordLevel').
Aspose.Words.Comparing.CompareOptions compareOptions = new Aspose.Words.Comparing.CompareOptions();
compareOptions.Granularity = granularity;

docA.Compare(docB, "author", DateTime.Now, compareOptions);

// La collection de groupes de révision du premier document contient toutes les différences entre les documents.
RevisionGroupCollection groups = docA.Revisions.Groups;
Assert.AreEqual(5, groups.Count);
```

### Voir également

* espace de noms [Aspose.Words.Comparing](../../aspose.words.comparing/)
* Assemblée [Aspose.Words](../../)


