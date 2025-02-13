---
title: TxtSaveOptions.ListIndentation
second_title: Référence de l'API Aspose.Words pour .NET
description: TxtSaveOptions propriété. Obtient un objet ListIndentation qui spécifie le nombre et le caractère à utiliser pour lindentation des niveaux de liste. Par défaut le nombre de caractères 0 est nul ce qui signifie quil ny a pas dindentation.
type: docs
weight: 30
url: /fr/net/aspose.words.saving/txtsaveoptions/listindentation/
---
## TxtSaveOptions.ListIndentation property

Obtient un objet ListIndentation qui spécifie le nombre et le caractère à utiliser pour l'indentation des niveaux de liste. Par défaut, le nombre de caractères '\0' est nul, ce qui signifie qu'il n'y a pas d'indentation.

```csharp
public TxtListIndentation ListIndentation { get; }
```

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

* class [TxtListIndentation](../../txtlistindentation/)
* class [TxtSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../txtsaveoptions/)
* Assemblée [Aspose.Words](../../../)


