---
title: Comment.Ancestor
second_title: Справочник по API Aspose.Words для .NET
description: Comment свойство. Возвращает родительский объект Comment. Возвращает null для комментариев верхнего уровня.
type: docs
weight: 20
url: /ru/net/aspose.words/comment/ancestor/
---
## Comment.Ancestor property

Возвращает родительский объект Comment. Возвращает null для комментариев верхнего уровня.

```csharp
public Comment Ancestor { get; }
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

* class [Comment](../)
* пространство имен [Aspose.Words](../../comment/)
* сборка [Aspose.Words](../../../)


