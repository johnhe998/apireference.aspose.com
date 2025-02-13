---
title: Body.EnsureMinimum
second_title: Aspose.Words for .NET API 参考
description: Body 方法. 如果最后一个孩子不是段落则创建并附加一个空段落
type: docs
weight: 50
url: /zh/net/aspose.words/body/ensureminimum/
---
## Body.EnsureMinimum method

如果最后一个孩子不是段落，则创建并附加一个空段落。

```csharp
public void EnsureMinimum()
```

### 例子

清除文档中所有部分的主要文本，留下部分本身。

```csharp
Document doc = new Document();

// 一个空白文档包含一个部分、一个正文和一个段落。
// 调用“RemoveAllChildren”方法来移除所有这些节点，
// 最后得到一个没有子节点的文档节点。
doc.RemoveAllChildren();

// 这个文档现在没有我们可以添加内容的复合子节点。
// 如果我们想编辑它，我们需要重新填充它的节点集合。
// 首先，创建一个新部分，然后将其作为子节点附加到根文档节点。
Section section = new Section(doc);
doc.AppendChild(section);

// 一个section需要一个body，它将包含并显示它的所有内容
// 在节的页眉和页脚之间的页面上。
Body body = new Body(doc);
section.AppendChild(body);

// 这个身体没有孩子，所以我们还不能给它添加运行。
Assert.AreEqual(0, doc.FirstSection.Body.GetChildNodes(NodeType.Any, true).Count);

// 调用“EnsureMinimum”以确保该正文至少包含一个空段落。 
body.EnsureMinimum();

// 现在，我们可以将运行添加到正文中，并让文档显示它们。
body.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### 也可以看看

* class [Body](../)
* 命名空间 [Aspose.Words](../../body/)
* 部件 [Aspose.Words](../../../)


