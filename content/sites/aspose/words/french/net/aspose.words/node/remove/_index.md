---
title: Node.Remove
second_title: Référence de l'API Aspose.Words pour .NET
description: Node méthode. Se supprime du parent.
type: docs
weight: 150
url: /fr/net/aspose.words/node/remove/
---
## Node.Remove method

Se supprime du parent.

```csharp
public void Remove()
```

### Exemples

Montre comment supprimer toutes les formes avec des images d'un document.

```csharp
Document doc = new Document(MyDir + "Images.docx");
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.OfType<Shape>().Count(s => s.HasImage));

foreach (Shape shape in shapes.OfType<Shape>())
    if (shape.HasImage) 
        shape.Remove();

Assert.AreEqual(0, shapes.OfType<Shape>().Count(s => s.HasImage));
```

Montre comment supprimer tous les nœuds enfants d'un type spécifique d'un nœud composite.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Assert.AreEqual(2, doc.GetChildNodes(NodeType.Table, true).Count);

Node curNode = doc.FirstSection.Body.FirstChild;

while (curNode != null)
{
    // Enregistre le nœud frère suivant en tant que variable au cas où nous voudrions y accéder après avoir supprimé ce nœud.
    Node nextNode = curNode.NextSibling;

    // Un corps de section peut contenir des nœuds Paragraphe et Table.
    // Si le nœud est une table, supprimez-le du parent.
    if (curNode.NodeType == NodeType.Table)
        curNode.Remove();

    curNode = nextNode;
}

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Table, true).Count);
```

### Voir également

* class [Node](../)
* espace de noms [Aspose.Words](../../node/)
* Assemblée [Aspose.Words](../../../)


