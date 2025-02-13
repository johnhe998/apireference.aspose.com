---
title: Document.EnsureMinimum
second_title: Aspose.Words for .NET API 参考
description: Document 方法. 如果文档不包含任何部分则创建一个包含一个段落的部分
type: docs
weight: 560
url: /zh/net/aspose.words/document/ensureminimum/
---
## Document.EnsureMinimum method

如果文档不包含任何部分，则创建一个包含一个段落的部分。

```csharp
public void EnsureMinimum()
```

### 例子

展示如何确保文档包含编辑其内容所需的最少节点集。

```csharp
// 一个新创建的文档包含一个子Section，其中包括一个子Body和一个子Paragraph。
// 我们可以通过在该段落中添加 Runs 或 inline Shapes 等节点来编辑文档正文的内容。
Document doc = new Document();
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);

Assert.AreEqual(NodeType.Section, nodes[0].NodeType);
Assert.AreEqual(doc, nodes[0].ParentNode);

Assert.AreEqual(NodeType.Body, nodes[1].NodeType);
Assert.AreEqual(nodes[0], nodes[1].ParentNode);

Assert.AreEqual(NodeType.Paragraph, nodes[2].NodeType);
Assert.AreEqual(nodes[1], nodes[2].ParentNode);

// 这是我们需要能够编辑文档的最小节点集。
// 如果我们删除其中任何一个，我们将无法再编辑文档。
doc.RemoveAllChildren();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Any, true).Count);

// 调用此方法以确保文档至少具有这三个节点，以便我们可以再次对其进行编辑。
doc.EnsureMinimum();

Assert.AreEqual(NodeType.Section, nodes[0].NodeType);
Assert.AreEqual(NodeType.Body, nodes[1].NodeType);
Assert.AreEqual(NodeType.Paragraph, nodes[2].NodeType);

((Paragraph)nodes[2]).Runs.Add(new Run(doc, "Hello world!"));
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


