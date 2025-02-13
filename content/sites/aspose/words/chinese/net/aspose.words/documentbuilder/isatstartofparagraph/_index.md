---
title: DocumentBuilder.IsAtStartOfParagraph
second_title: Aspose.Words for .NET API 参考
description: DocumentBuilder 财产. 如果光标位于当前段落的开头光标之前没有文本则返回 true
type: docs
weight: 110
url: /zh/net/aspose.words/documentbuilder/isatstartofparagraph/
---
## DocumentBuilder.IsAtStartOfParagraph property

如果光标位于当前段落的开头（光标之前没有文本），则返回 true。

```csharp
public bool IsAtStartOfParagraph { get; }
```

### 例子

显示如何将文档构建器的光标移动到文档中的不同节点。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 创建一个有效的书签，一个由书签开始节点包围的节点组成的实体，
 // 和一个书签结束节点。
builder.StartBookmark("MyBookmark");
builder.Write("Bookmark contents.");
builder.EndBookmark("MyBookmark");

NodeCollection firstParagraphNodes = doc.FirstSection.Body.FirstParagraph.ChildNodes;

Assert.AreEqual(NodeType.BookmarkStart, firstParagraphNodes[0].NodeType);
Assert.AreEqual(NodeType.Run, firstParagraphNodes[1].NodeType);
Assert.AreEqual("Bookmark contents.", firstParagraphNodes[1].GetText().Trim());
Assert.AreEqual(NodeType.BookmarkEnd, firstParagraphNodes[2].NodeType);

// 文档构建器的光标始终位于我们最后添加的节点之前。
// 如果构建器的光标位于文档的末尾，则其当前节点将为空。
// 上一个节点是我们最后添加的书签结束节点。
// 使用构建器添加新节点会将它们附加到最后一个节点。
Assert.Null(builder.CurrentNode);

// 如果我们希望使用构建器编辑文档的不同部分，
// 我们需要把它的光标带到我们想要编辑的节点上。
builder.MoveToBookmark("MyBookmark");

// 将其移动到书签会将其移动到书签开始和结束节点中的第一个节点，即封闭的运行。
Assert.AreEqual(firstParagraphNodes[1], builder.CurrentNode);

// 我们也可以像这样将光标移动到单个节点上。
builder.MoveTo(doc.FirstSection.Body.FirstParagraph.GetChildNodes(NodeType.Any, false)[0]);

Assert.AreEqual(NodeType.BookmarkStart, builder.CurrentNode.NodeType);
Assert.AreEqual(doc.FirstSection.Body.FirstParagraph, builder.CurrentParagraph);
Assert.IsTrue(builder.IsAtStartOfParagraph);

// 我们可以使用特定的方法移动到文档的开头/结尾。
builder.MoveToDocumentEnd();

Assert.IsTrue(builder.IsAtEndOfParagraph);

builder.MoveToDocumentStart();

Assert.IsTrue(builder.IsAtStartOfParagraph);
```

### 也可以看看

* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)


