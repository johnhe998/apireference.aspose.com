---
title: StructuredDocumentTagRangeStart.ChildNodes
second_title: Aspose.Words for .NET API 参考
description: StructuredDocumentTagRangeStart 财产. 获取此范围开始节点和范围结束节点之间的所有节点
type: docs
weight: 20
url: /zh/net/aspose.words.markup/structureddocumenttagrangestart/childnodes/
---
## StructuredDocumentTagRangeStart.ChildNodes property

获取此范围开始节点和范围结束节点之间的所有节点。

```csharp
public NodeCollection ChildNodes { get; }
```

### 例子

展示如何获取 StructuredDocumentTagRangeStart 的子节点。

```csharp
Document doc = new Document(MyDir + "Multi-section structured document tags.docx");
StructuredDocumentTagRangeStart tag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true)[0] as StructuredDocumentTagRangeStart;

Console.WriteLine("StructuredDocumentTagRangeStart values:");
Console.WriteLine($"\t|Child nodes count: {tag.ChildNodes.Count}\n");

foreach (Node node in tag.ChildNodes)
    Console.WriteLine($"\t|Child node type: {node.NodeType}");

foreach (Node node in tag.GetChildNodes(NodeType.Run, true))
    Console.WriteLine($"\t|Child node text: {node.GetText()}");
```

### 也可以看看

* class [NodeCollection](../../../aspose.words/nodecollection/)
* class [StructuredDocumentTagRangeStart](../)
* 命名空间 [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* 部件 [Aspose.Words](../../../)


