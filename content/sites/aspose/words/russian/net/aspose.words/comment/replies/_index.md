---
title: Comment.Replies
second_title: Справочник по API Aspose.Words для .NET
description: Comment свойство. Возвращает коллекциюComment объекты которые являются непосредственными дочерними элементами указанного комментария.
type: docs
weight: 90
url: /ru/net/aspose.words/comment/replies/
---
## Comment.Replies property

Возвращает коллекцию[`Comment`](../) объекты, которые являются непосредственными дочерними элементами указанного комментария.

```csharp
public CommentCollection Replies { get; }
```

### Примеры

Показывает, как распечатать все комментарии к документу и ответы на них.

```csharp
Document doc = new Document(MyDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

// Если у комментария нет предка, это комментарий «верхнего уровня», а не комментарий типа ответа.
// Печатать все комментарии верхнего уровня вместе с любыми ответами, которые они могут иметь.
foreach (Comment comment in comments.OfType<Comment>().Where(c => c.Ancestor == null))
{
    Console.WriteLine("Top-level comment:");
    Console.WriteLine($"\t\"{comment.GetText().Trim()}\", by {comment.Author}");
    Console.WriteLine($"Has {comment.Replies.Count} replies");
    foreach (Comment commentReply in comment.Replies)
    {
        Console.WriteLine($"\t\"{commentReply.GetText().Trim()}\", by {commentReply.Author}");
    }
    Console.WriteLine();
}
```

### Смотрите также

* class [CommentCollection](../../commentcollection/)
* class [Comment](../)
* пространство имен [Aspose.Words](../../comment/)
* сборка [Aspose.Words](../../../)


