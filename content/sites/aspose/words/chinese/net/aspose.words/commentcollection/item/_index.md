---
title: CommentCollection.Item
second_title: Aspose.Words for .NET API 参考
description: CommentCollection 财产. 检索一个 评论在给定的索引处
type: docs
weight: 10
url: /zh/net/aspose.words/commentcollection/item/
---
## CommentCollection indexer

检索一个 **评论**在给定的索引处。

```csharp
public Comment this[int index] { get; }
```

| 范围 | 描述 |
| --- | --- |
| index | 集合中的索引。 |

### 评论

该索引从零开始。

允许使用负索引并指示从集合的背面进行访问。 例如 -1 表示最后一项，-2 表示倒数第二个，依此类推。

如果 index 大于或等于列表中的项目数，则返回空引用。

如果 index 为负且其绝对值大于列表中的项目数，则返回空引用。

### 例子

显示如何删除评论回复。

```csharp
Document doc = new Document();

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");

doc.FirstSection.Body.FirstParagraph.AppendChild(comment);

comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "New reply");
comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "Another reply");

Assert.AreEqual(2, comment.Replies.Count()); 

// 下面是从评论中删除回复的两种方法。
// 1 - 使用“RemoveReply”方法从评论中单独删除回复：
comment.RemoveReply(comment.Replies[0]);

Assert.AreEqual(1, comment.Replies.Count());

// 2 - 使用“RemoveAllReplies”方法一次删除评论中的所有回复：
comment.RemoveAllReplies();

Assert.AreEqual(0, comment.Replies.Count());
```

### 也可以看看

* class [Comment](../../comment/)
* class [CommentCollection](../)
* 命名空间 [Aspose.Words](../../commentcollection/)
* 部件 [Aspose.Words](../../../)


