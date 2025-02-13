---
title: Node.NodeTypeToString
second_title: Aspose.Words for .NET API 参考
description: Node 方法. 一种将节点类型枚举值转换为用户友好字符串的实用方法
type: docs
weight: 170
url: /zh/net/aspose.words/node/nodetypetostring/
---
## Node.NodeTypeToString method

一种将节点类型枚举值转换为用户友好字符串的实用方法。

```csharp
public static string NodeTypeToString(NodeType nodeType)
```

### 例子

演示如何使用节点的 NextSibling 属性枚举其直接子级。

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

* enum [NodeType](../../nodetype/)
* class [Node](../)
* 命名空间 [Aspose.Words](../../node/)
* 部件 [Aspose.Words](../../../)


