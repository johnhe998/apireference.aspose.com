---
title: Node.NextPreOrder
second_title: Aspose.Words für .NET-API-Referenz
description: Node methode. Ruft den nächsten Knoten gemäß dem Traversalalgorithmus des Vorbestellungsbaums ab.
type: docs
weight: 130
url: /de/net/aspose.words/node/nextpreorder/
---
## Node.NextPreOrder method

Ruft den nächsten Knoten gemäß dem Traversalalgorithmus des Vorbestellungsbaums ab.

```csharp
public Node NextPreOrder(Node rootNode)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| rootNode | Node | Der oberste Knoten (Limit) des Durchlaufs. |

### Rückgabewert

Nächster Knoten in der Vorbestellungsreihenfolge. Null, wenn der RootNode erreicht wurde.

### Beispiele

Zeigt, wie die Knotenstruktur des Dokuments mithilfe des Vorbestellungs-Traversierungsalgorithmus durchlaufen und alle gefundenen Formen mit einem Bild gelöscht werden.

```csharp
Document doc = new Document(MyDir + "Images.docx");

Assert.AreEqual(9, 
    doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().Count(s => s.HasImage));

Node curNode = doc;
while (curNode != null)
{
    Node nextNode = curNode.NextPreOrder(doc);

    if (curNode.PreviousPreOrder(doc) != null && nextNode != null)
        Assert.AreEqual(curNode, nextNode.PreviousPreOrder(doc));

    if (curNode.NodeType == NodeType.Shape && ((Shape)curNode).HasImage)
        curNode.Remove();

    curNode = nextNode;
}

Assert.AreEqual(0,
    doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().Count(s => s.HasImage));
```

### Siehe auch

* class [Node](../)
* namensraum [Aspose.Words](../../node/)
* Montage [Aspose.Words](../../../)


