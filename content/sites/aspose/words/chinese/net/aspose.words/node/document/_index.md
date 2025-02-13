---
title: Node.Document
second_title: Aspose.Words for .NET API 参考
description: Node 财产. 获取该节点所属的文档
type: docs
weight: 20
url: /zh/net/aspose.words/node/document/
---
## Node.Document property

获取该节点所属的文档。

```csharp
public virtual DocumentBase Document { get; }
```

### 评论

该节点始终属于一个文档，即使它刚刚创建 并且尚未添加到树中，或者它已从树中删除。

### 例子

展示如何创建节点并设置其所属文档。

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
para.AppendChild(new Run(doc, "Hello world!"));

// 我们还没有将此段落作为子节点附加到任何复合节点。
Assert.IsNull(para.ParentNode);

// 如果一个节点是另一个复合节点的合适的子节点类型，
// 只有当两个节点具有相同的所有者文档时，我们才能将其作为子节点附加。
// 所有者文档是我们传递给节点构造函数的文档。
// 我们没有将此段落附加到文档中，因此文档不包含其文本。
Assert.AreEqual(para.Document, doc);
Assert.AreEqual(string.Empty, doc.GetText().Trim());

// 由于文档拥有这个段落，我们可以将它的一种样式应用于段落的内容。
para.ParagraphFormat.Style = doc.Styles["Heading 1"];

// 将此节点添加到文档中，然后验证其内容。
doc.FirstSection.Body.AppendChild(para);

Assert.AreEqual(doc.FirstSection.Body, para.ParentNode);
Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### 也可以看看

* class [DocumentBase](../../documentbase/)
* class [Node](../)
* 命名空间 [Aspose.Words](../../node/)
* 部件 [Aspose.Words](../../../)


