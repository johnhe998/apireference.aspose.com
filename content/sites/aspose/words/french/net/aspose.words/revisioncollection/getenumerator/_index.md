---
title: RevisionCollection.GetEnumerator
second_title: Référence de l'API Aspose.Words pour .NET
description: RevisionCollection méthode. Renvoie un objet énumérateur.
type: docs
weight: 50
url: /fr/net/aspose.words/revisioncollection/getenumerator/
---
## RevisionCollection.GetEnumerator method

Renvoie un objet énumérateur.

```csharp
public IEnumerator<Revision> GetEnumerator()
```

### Exemples

Montre comment travailler avec la collection de révisions d'un document.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
RevisionCollection revisions = doc.Revisions;

// Cette collection elle-même a une collection de groupes de révision.
// Chaque groupe est une séquence de révisions adjacentes.
Console.WriteLine($"{revisions.Groups.Count} revision groups:");

// Itérer sur la collection de groupes et imprimer le texte concerné par la révision.
using (IEnumerator<RevisionGroup> e = revisions.Groups.GetEnumerator())
{
    while (e.MoveNext())
    {
        Console.WriteLine($"\tGroup type \"{e.Current.RevisionType}\", " +
                          $"author: {e.Current.Author}, contents: [{e.Current.Text.Trim()}]");
    }
}

// Chaque exécution affectée par une révision obtient un objet de révision correspondant.
// La collection des révisions est considérablement plus grande que la forme condensée que nous avons imprimée ci-dessus,
// en fonction du nombre d'exécutions dans lesquelles nous avons segmenté le document lors de l'édition de Microsoft Word.
Console.WriteLine($"\n{revisions.Count} revisions:");

using (IEnumerator<Revision> e = revisions.GetEnumerator())
{
    while (e.MoveNext())
    {
        // Un StyleDefinitionChange affecte strictement les styles et non les nœuds de document. Cela signifie le "ParentStyle"
        // la propriété sera toujours utilisée, tandis que le ParentNode sera toujours nul.
        // Étant donné que toutes les autres modifications affectent les nœuds, ParentNode sera à l'inverse utilisé et ParentStyle sera nul.
        if (e.Current.RevisionType == RevisionType.StyleDefinitionChange)
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, style: [{e.Current.ParentStyle.Name}]");
        }
        else
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, contents: [{e.Current.ParentNode.GetText().Trim()}]");
        }
    }
}

// Rejette toutes les révisions via la collection, ramenant le document à sa forme d'origine.
revisions.RejectAll();

Assert.AreEqual(0, revisions.Count);
```

### Voir également

* class [Revision](../../revision/)
* class [RevisionCollection](../)
* espace de noms [Aspose.Words](../../revisioncollection/)
* Assemblée [Aspose.Words](../../../)


