---
title: Comment.SetText
second_title: Aspose.Words for .NET API 参考
description: Comment 方法. 这是一种方便的方法可以轻松设置评论的文本
type: docs
weight: 150
url: /zh/net/aspose.words/comment/settext/
---
## Comment.SetText method

这是一种方便的方法，可以轻松设置评论的文本。

```csharp
public void SetText(string text)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| text | String | 评论的新文本。 |

### 评论

此方法允许从字符串中快速设置注释文本。字符串可以包含 分段符，这将在评论中相应地创建文本段落。 如果您想在评论中插入更复杂的元素，例如书签 或表格或应用丰富的格式，那么您需要使用适当的节点类到 建立评论文本。

### 例子

演示如何向文档添加评论，然后对其进行回复。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");

// 将注释放在文档正文中的一个节点上。
// 此注释将显示在其段落的位置，
// 在页面的右侧边距之外，并用虚线将其连接到其段落。
builder.CurrentParagraph.AppendChild(comment);

// 添加一个回复，该回复将显示在其父评论下方。
comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "New reply");

// 评论和回复都是评论节点。
Assert.AreEqual(2, doc.GetChildNodes(NodeType.Comment, true).Count);

// 不回复其他评论的评论是“顶级的”。他们没有祖先的评论。
Assert.Null(comment.Ancestor);

// 回复有一个祖先的顶级评论。
Assert.AreEqual(comment, comment.Replies[0].Ancestor);

doc.Save(ArtifactsDir + "Comment.AddCommentWithReply.docx");
```

### 也可以看看

* class [Comment](../)
* 命名空间 [Aspose.Words](../../comment/)
* 部件 [Aspose.Words](../../../)


