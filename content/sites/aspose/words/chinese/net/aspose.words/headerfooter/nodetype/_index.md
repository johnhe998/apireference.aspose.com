---
title: HeaderFooter.NodeType
second_title: Aspose.Words for .NET API 参考
description: HeaderFooter 财产. 返回 NodeType.HeaderFooter.
type: docs
weight: 50
url: /zh/net/aspose.words/headerfooter/nodetype/
---
## HeaderFooter.NodeType property

返回 **NodeType.HeaderFooter**.

```csharp
public override NodeType NodeType { get; }
```

### 例子

展示如何遍历复合节点的子节点。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Primary header");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("Primary footer");

Section section = doc.FirstSection;

// 一个Section是一个复合节点，可以包含子节点，
// 但前提是这些子节点是“Body”或“HeaderFooter”节点类型。
foreach (Node node in section)
{
    switch (node.NodeType)
    {
        case NodeType.Body:
        {
            Body body = (Body)node;

            Console.WriteLine("Body:");
            Console.WriteLine($"\t\"{body.GetText().Trim()}\"");
            break;
        }
        case NodeType.HeaderFooter:
        {
            HeaderFooter headerFooter = (HeaderFooter)node;

            Console.WriteLine($"HeaderFooter type: {headerFooter.HeaderFooterType}:");
            Console.WriteLine($"\t\"{headerFooter.GetText().Trim()}\"");
            break;
        }
        default:
        {
            throw new Exception("Unexpected node type in a section.");
        }
    }
}
```

### 也可以看看

* enum [NodeType](../../nodetype/)
* class [HeaderFooter](../)
* 命名空间 [Aspose.Words](../../headerfooter/)
* 部件 [Aspose.Words](../../../)


