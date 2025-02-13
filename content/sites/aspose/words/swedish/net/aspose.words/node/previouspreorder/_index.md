---
title: Node.PreviousPreOrder
second_title: Aspose.Words för .NET API Referens
description: Node metod. Hämtar föregående nod enligt algoritmen för förbeställningsträdet.
type: docs
weight: 140
url: /sv/net/aspose.words/node/previouspreorder/
---
## Node.PreviousPreOrder method

Hämtar föregående nod enligt algoritmen för förbeställningsträdet.

```csharp
public Node PreviousPreOrder(Node rootNode)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| rootNode | Node | Den övre noden (gränsen) för traversering. |

### Returvärde

Föregående nod i förbeställning. Null om nått rootNode.

### Exempel

Visar hur man går igenom dokumentets nodträd med förbeställnings-genomgångsalgoritmen och tar bort alla former som påträffas med en bild.

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

### Se även

* class [Node](../)
* namnutrymme [Aspose.Words](../../node/)
* hopsättning [Aspose.Words](../../../)


