---
title: Section.NodeType
second_title: Aspose.Words für .NET-API-Referenz
description: Section eigendom. gibt zurück NodeType.Section .
type: docs
weight: 40
url: /de/net/aspose.words/section/nodetype/
---
## Section.NodeType property

gibt zurück **NodeType.Section** .

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
* class [Section](../)
* namensraum [Aspose.Words](../../section/)
* Montage [Aspose.Words](../../../)


