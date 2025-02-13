---
title: RevisionGroup.Author
second_title: Référence de l'API Aspose.Words pour .NET
description: RevisionGroup propriété. Obtient lauteur de ce groupe de révision.
type: docs
weight: 10
url: /fr/net/aspose.words/revisiongroup/author/
---
## RevisionGroup.Author property

Obtient l'auteur de ce groupe de révision.

```csharp
public string Author { get; }
```

### Exemples

Montre comment imprimer des informations sur un groupe de révisions dans un document.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

Assert.AreEqual(7, doc.Revisions.Groups.Count);

foreach (RevisionGroup group in doc.Revisions.Groups)
{
    Console.WriteLine(
        $"Revision author: {group.Author}; Revision type: {group.RevisionType} \n\tRevision text: {group.Text}");
}
```

### Voir également

* class [RevisionGroup](../)
* espace de noms [Aspose.Words](../../revisiongroup/)
* Assemblée [Aspose.Words](../../../)


