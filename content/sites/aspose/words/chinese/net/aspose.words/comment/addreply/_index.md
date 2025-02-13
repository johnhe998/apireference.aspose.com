---
title: Comment.AddReply
second_title: Aspose.Words for .NET API 参考
description: Comment 方法. 对此评论添加回复
type: docs
weight: 120
url: /zh/net/aspose.words/comment/addreply/
---
## Comment.AddReply method

对此评论添加回复。

```csharp
public Comment AddReply(string author, string initial, DateTime dateTime, string text)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| author | String | 回复的作者姓名。 |
| initial | String | 回复的作者姓名缩写。 |
| dateTime | DateTime | 回复的日期和时间。 |
| text | String | 回复文字。 |

### 返回值

创建的[`Comment`](../)回复的节点。

### 评论

由于现有的 MS Office 限制，文档中仅允许 1 级回复。 类型异常InvalidOperationException如果在现有回复评论上调用此方法 ，将引发此方法。

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


