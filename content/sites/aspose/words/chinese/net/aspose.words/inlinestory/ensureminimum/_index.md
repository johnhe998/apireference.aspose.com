---
title: InlineStory.EnsureMinimum
second_title: Aspose.Words for .NET API 参考
description: InlineStory 方法. 如果最后一个孩子不是段落则创建并附加一个空段落
type: docs
weight: 120
url: /zh/net/aspose.words/inlinestory/ensureminimum/
---
## InlineStory.EnsureMinimum method

如果最后一个孩子不是段落，则创建并附加一个空段落。

```csharp
public void EnsureMinimum()
```

### 例子

显示如何插入 InlineStory 节点。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, null);

// 表格节点有一个“EnsureMinimum()”方法，可以确保表格至少有一个单元格。
Table table = new Table(doc);
table.EnsureMinimum();

// 我们可以在脚注中放置一个表格，这将使它出现在引用页面的页脚处。
Assert.That(footnote.Tables, Is.Empty);
footnote.AppendChild(table);
Assert.AreEqual(1, footnote.Tables.Count);
Assert.AreEqual(NodeType.Table, footnote.LastChild.NodeType);

// InlineStory 也有一个“EnsureMinimum()”方法，但是在这种情况下，
// 它确保节点的最后一个子节点是一个段落，
// 让我们能够在 Microsoft Word 中轻松单击和书写文本。
footnote.EnsureMinimum();
Assert.AreEqual(NodeType.Paragraph, footnote.LastChild.NodeType);

// 编辑anchor的外观，也就是小上标数字
// 在指向脚注的正文中。
footnote.Font.Name = "Arial";
footnote.Font.Color = Color.Green;

// 所有内联故事节点都有各自的故事类型。
Assert.AreEqual(StoryType.Footnotes, footnote.StoryType);

// 评论是另一种类型的内联故事。
Comment comment = (Comment)builder.CurrentParagraph.AppendChild(new Comment(doc, "John Doe", "J. D.", DateTime.Now));

// 内联故事节点的父段落将来自主文档正文。
Assert.AreEqual(doc.FirstSection.Body.FirstParagraph, comment.ParentParagraph);

// 但是，最后一段是评论文本内容中的一段，
// 它将位于主文档正文之外的对话气泡中。
// 默认情况下，评论不会有任何子节点，
// 所以我们也可以应用 EnsureMinimum() 方法在这里放置一个段落。
Assert.Null(comment.LastParagraph);
comment.EnsureMinimum();
Assert.AreEqual(NodeType.Paragraph, comment.LastChild.NodeType);

// 一旦我们有了一个段落，我们就可以移动构建器来完成它并写下我们的评论。
builder.MoveTo(comment.LastParagraph);
builder.Write("My comment.");

Assert.AreEqual(StoryType.Comments, comment.StoryType);

doc.Save(ArtifactsDir + "InlineStory.InsertInlineStoryNodes.docx");
```

### 也可以看看

* class [InlineStory](../)
* 命名空间 [Aspose.Words](../../inlinestory/)
* 部件 [Aspose.Words](../../../)


