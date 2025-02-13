---
title: Section.EnsureMinimum
second_title: Aspose.Words for .NET API 参考
description: Section 方法. 确保该部分有正文和一个段落
type: docs
weight: 130
url: /zh/net/aspose.words/section/ensureminimum/
---
## Section.EnsureMinimum method

确保该部分有正文和一个段落。

```csharp
public void EnsureMinimum()
```

### 例子

显示如何准备新的节节点进行编辑。

```csharp
Document doc = new Document();

// 一个空白文档带有一个部分，它有一个正文，而正文又是一个段落。
// 我们可以通过向该段落添加文本、形状或表格等元素来向该文档添加内容。
Assert.AreEqual(NodeType.Section, doc.GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Body, doc.Sections[0].GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Paragraph, doc.Sections[0].Body.GetChild(NodeType.Any, 0, true).NodeType);

// 如果我们像这样添加一个新部分，它将没有正文或任何其他子节点。
doc.Sections.Add(new Section(doc));

Assert.AreEqual(0, doc.Sections[1].GetChildNodes(NodeType.Any, true).Count);

// 运行“EnsureMinimum”方法，将正文和段落添加到此部分以开始编辑。
doc.LastSection.EnsureMinimum();

Assert.AreEqual(NodeType.Body, doc.Sections[1].GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Paragraph, doc.Sections[1].Body.GetChild(NodeType.Any, 0, true).NodeType);

doc.Sections[0].Body.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### 也可以看看

* class [Section](../)
* 命名空间 [Aspose.Words](../../section/)
* 部件 [Aspose.Words](../../../)


