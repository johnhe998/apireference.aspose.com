---
title: Row.NodeType
second_title: Référence de l'API Aspose.Words pour .NET
description: Row propriété. Retours NodeType.Row .
type: docs
weight: 70
url: /fr/net/aspose.words.tables/row/nodetype/
---
## Row.NodeType property

Retours **NodeType.Row** .

```csharp
public override NodeType NodeType { get; }
```

### Exemples

Montre comment parcourir l'arborescence des nœuds enfants d'un nœud composite.

```csharp
{
    Document doc = new Document(MyDir + "Paragraphs.docx");

    // Tout nœud pouvant contenir des nœuds enfants, comme le document lui-même, est composite.
    Assert.True(doc.IsComposite);

    // Invoque la fonction récursive qui parcourra et imprimera tous les nœuds enfants d'un nœud composite.
    TraverseAllNodes(doc, 0);
}

/// <summary>
/// Parcourt récursivement une arborescence de nœuds tout en affichant le type de chaque nœud
/// avec un retrait en fonction de la profondeur ainsi que du contenu de tous les nœuds en ligne.
/// </summary>
public void TraverseAllNodes(CompositeNode parentNode, int depth)
{
    for (Node childNode = parentNode.FirstChild; childNode != null; childNode = childNode.NextSibling)
    {
        Console.Write($"{new string('\t', depth)}{Node.NodeTypeToString(childNode.NodeType)}");

        // Recurse dans le nœud s'il s'agit d'un nœud composite. Sinon, imprimez son contenu s'il s'agit d'un nœud en ligne.
        if (childNode.IsComposite)
        {
            Console.WriteLine();
            TraverseAllNodes((CompositeNode)childNode, depth + 1);
        }
        else if (childNode is Inline)
        {
            Console.WriteLine($" - \"{childNode.GetText().Trim()}\"");
        }
        else
        {
            Console.WriteLine();
        }
    }
}
```

### Voir également

* enum [NodeType](../../../aspose.words/nodetype/)
* class [Row](../)
* espace de noms [Aspose.Words.Tables](../../row/)
* Assemblée [Aspose.Words](../../../)


