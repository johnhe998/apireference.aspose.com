---
title: Node.NodeTypeToString
second_title: Aspose.Words for .NET API Referansı
description: Node yöntem. Düğüm türü numaralandırma değerini kullanıcı dostu bir dizeye dönüştüren yardımcı program yöntemi.
type: docs
weight: 170
url: /tr/net/aspose.words/node/nodetypetostring/
---
## Node.NodeTypeToString method

Düğüm türü numaralandırma değerini kullanıcı dostu bir dizeye dönüştüren yardımcı program yöntemi.

```csharp
public static string NodeTypeToString(NodeType nodeType)
```

### Örnekler

Bir düğümün NextSibling özelliğinin, doğrudan alt öğeleri arasında numaralandırmak için nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

for (Node node = doc.FirstSection.Body.FirstChild; node != null; node = node.NextSibling)
{
    Console.WriteLine();
    Console.WriteLine($"Node type: {Node.NodeTypeToString(node.NodeType)}");

    string contents = node.GetText().Trim();
    Console.WriteLine(contents == string.Empty ? "This node contains no text" : $"Contents: \"{node.GetText().Trim()}\"");
}
```

Bir bileşik düğümün alt düğümler ağacında nasıl geçileceğini gösterir.

```csharp
{
    Document doc = new Document(MyDir + "Paragraphs.docx");

    // Belgenin kendisi gibi alt düğümler içerebilen herhangi bir düğüm bileşiktir.
    Assert.True(doc.IsComposite);

    // Bir bileşik düğümün tüm alt düğümlerini geçecek ve yazdıracak özyinelemeli işlevi çağırın.
    TraverseAllNodes(doc, 0);
}

/// <summary>
/// Her bir düğümün türünü yazdırırken bir düğüm ağacında yinelemeli olarak geçer
/// tüm satır içi düğümlerin içeriğinin yanı sıra derinliğe bağlı bir girinti ile.
/// </summary>
public void TraverseAllNodes(CompositeNode parentNode, int depth)
{
    for (Node childNode = parentNode.FirstChild; childNode != null; childNode = childNode.NextSibling)
    {
        Console.Write($"{new string('\t', depth)}{Node.NodeTypeToString(childNode.NodeType)}");

        // Bileşik bir düğümse, düğüme tekrar gir. Aksi takdirde, bir satır içi düğüm ise içeriğini yazdırın.
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

### Ayrıca bakınız

* enum [NodeType](../../nodetype/)
* class [Node](../)
* ad alanı [Aspose.Words](../../node/)
* toplantı [Aspose.Words](../../../)


