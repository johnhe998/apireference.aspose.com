---
title: Document.NodeType
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. gibt zurück Knotentyp.Dokument .
type: docs
weight: 260
url: /de/net/aspose.words/document/nodetype/
---
## Document.NodeType property

gibt zurück **Knotentyp.Dokument** .

```csharp
public override NodeType NodeType { get; }
```

### Beispiele

Zeigt, wie die Baumstruktur untergeordneter Knoten eines zusammengesetzten Knotens durchlaufen wird.

```csharp
{
    Document doc = new Document(MyDir + "Paragraphs.docx");

    // Jeder Knoten, der untergeordnete Knoten enthalten kann, wie z. B. das Dokument selbst, ist zusammengesetzt.
    Assert.True(doc.IsComposite);

    // Rufen Sie die rekursive Funktion auf, die alle untergeordneten Knoten eines zusammengesetzten Knotens durchläuft und ausgibt.
    TraverseAllNodes(doc, 0);
}

/// <summary>
/// Durchläuft rekursiv einen Knotenbaum, während der Typ jedes Knotens ausgegeben wird
/// mit einem Einzug in Abhängigkeit von der Tiefe sowie den Inhalten aller Inline-Knoten.
/// </summary>
public void TraverseAllNodes(CompositeNode parentNode, int depth)
{
    for (Node childNode = parentNode.FirstChild; childNode != null; childNode = childNode.NextSibling)
    {
        Console.Write($"{new string('\t', depth)}{Node.NodeTypeToString(childNode.NodeType)}");

        // Rekursion in den Knoten, wenn es sich um einen zusammengesetzten Knoten handelt. Geben Sie andernfalls seinen Inhalt aus, wenn es sich um einen Inline-Knoten handelt.
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

### Siehe auch

* enum [NodeType](../../nodetype/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


