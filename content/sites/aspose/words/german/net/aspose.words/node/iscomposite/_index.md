---
title: Node.IsComposite
second_title: Aspose.Words für .NET-API-Referenz
description: Node eigendom. Gibt wahr zurück wenn dieser Knoten andere Knoten enthalten kann.
type: docs
weight: 30
url: /de/net/aspose.words/node/iscomposite/
---
## Node.IsComposite property

Gibt wahr zurück, wenn dieser Knoten andere Knoten enthalten kann.

```csharp
public virtual bool IsComposite { get; }
```

### Eigentumswert

Diese Methode gibt false zurück, da Node keine untergeordneten Knoten haben kann.

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

* class [Node](../)
* namensraum [Aspose.Words](../../node/)
* Montage [Aspose.Words](../../../)


