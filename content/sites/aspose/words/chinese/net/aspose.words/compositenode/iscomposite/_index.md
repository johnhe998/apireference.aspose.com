---
title: CompositeNode.IsComposite
second_title: Aspose.Words for .NET API 参考
description: CompositeNode 财产. 返回真因为该节点可以有子节点
type: docs
weight: 50
url: /zh/net/aspose.words/compositenode/iscomposite/
---
## CompositeNode.IsComposite property

返回真，因为该节点可以有子节点。

```csharp
public override bool IsComposite { get; }
```

### 例子

显示如何遍历复合节点的子节点树。

```csharp
{
    Document doc = new Document(MyDir + "Paragraphs.docx");

    // 任何可以包含子节点的节点，例如文档本身，都是复合的。
    Assert.True(doc.IsComposite);

    // 调用将遍历并打印复合节点的所有子节点的递归函数。
    TraverseAllNodes(doc, 0);
}

/// <summary>
/// 递归遍历一个节点树，同时打印每个节点的类型
/// 缩进取决于深度以及所有内联节点的内容。
/// </summary>
public void TraverseAllNodes(CompositeNode parentNode, int depth)
{
    for (Node childNode = parentNode.FirstChild; childNode != null; childNode = childNode.NextSibling)
    {
        Console.Write($"{new string('\t', depth)}{Node.NodeTypeToString(childNode.NodeType)}");

        // 如果是复合节点，则递归到该节点。否则，如果它是内联节点，则打印其内容。
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

### 也可以看看

* class [CompositeNode](../)
* 命名空间 [Aspose.Words](../../compositenode/)
* 部件 [Aspose.Words](../../../)


