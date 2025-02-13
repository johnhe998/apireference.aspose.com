---
title: Class TxtListIndentation
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.TxtListIndentation classe. Spécifie comment les niveaux de liste sont en retrait lorsque le document est exporté versText format.
type: docs
weight: 5370
url: /fr/net/aspose.words.saving/txtlistindentation/
---
## TxtListIndentation class

Spécifie comment les niveaux de liste sont en retrait lorsque le document est exporté versText format.

```csharp
public class TxtListIndentation
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [TxtListIndentation](txtlistindentation/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [Character](../../aspose.words.saving/txtlistindentation/character/) { get; set; } | Obtient ou définit le caractère à utiliser pour l'indentation des niveaux de liste. La valeur par défaut est '\0', cela signifie qu'il n'y a pas d'indentation. |
| [Count](../../aspose.words.saving/txtlistindentation/count/) { get; set; } | Obtient ou définit le nombre[`Character`](./character/) à utiliser comme indentation par niveau de liste. La valeur par défaut est 0, cela signifie qu'il n'y a pas d'indentation. |

### Exemples

Montre comment configurer l'indentation de la liste lors de l'enregistrement d'un document en texte brut.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crée une liste avec trois niveaux d'indentation.
builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.ListFormat.ListIndent();
builder.Writeln("Item 2");
builder.ListFormat.ListIndent(); 
builder.Write("Item 3");

// Crée un objet "TxtSaveOptions", que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont nous enregistrons le document en texte brut.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// Définissez la propriété "Caractère" pour attribuer un caractère à utiliser
// pour le rembourrage qui simule l'indentation de la liste en clair.
txtSaveOptions.ListIndentation.Character = ' ';

// Définissez la propriété "Count" pour spécifier le nombre de fois
// pour placer le caractère de remplissage pour chaque niveau d'indentation de la liste.
txtSaveOptions.ListIndentation.Count = 3;

doc.Save(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt");

Assert.AreEqual("1. Item 1\r\n" +
                "   a. Item 2\r\n" +
                "      i. Item 3\r\n", docText);
```

### Voir également

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


