---
title: Range.Delete
second_title: Référence de l'API Aspose.Words pour .NET
description: Range méthode. Supprime tous les caractères de la plage.
type: docs
weight: 60
url: /fr/net/aspose.words/range/delete/
---
## Range.Delete method

Supprime tous les caractères de la plage.

```csharp
public void Delete()
```

### Exemples

Montre comment supprimer tous les nœuds d'une plage.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ajoutez du texte à la première section du document, puis ajoutez une autre section.
builder.Write("Section 1. ");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Write("Section 2.");

Assert.AreEqual("Section 1. \fSection 2.", doc.GetText().Trim());

// Supprimer entièrement la première section en supprimant tous les nœuds
// dans sa plage, y compris la section elle-même.
doc.Sections[0].Range.Delete();

Assert.AreEqual(1, doc.Sections.Count);
Assert.AreEqual("Section 2.", doc.GetText().Trim());
```

### Voir également

* class [Range](../)
* espace de noms [Aspose.Words](../../range/)
* Assemblée [Aspose.Words](../../../)


