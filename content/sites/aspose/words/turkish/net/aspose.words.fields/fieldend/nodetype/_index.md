---
title: FieldEnd.NodeType
second_title: Aspose.Words for .NET API Referansı
description: FieldEnd mülk. İadeFieldEnd .
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldend/nodetype/
---
## FieldEnd.NodeType property

İadeFieldEnd .

```csharp
public override NodeType NodeType { get; }
```

### Örnekler

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

* enum [NodeType](../../../aspose.words/nodetype/)
* class [FieldEnd](../)
* ad alanı [Aspose.Words.Fields](../../fieldend/)
* toplantı [Aspose.Words](../../../)


