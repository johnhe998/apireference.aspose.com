---
title: Comment.Author
second_title: Aspose.Words لمراجع .NET API
description: Comment ملكية. إرجاع أو تعيين اسم المؤلف للتعليق.
type: docs
weight: 30
url: /ar/net/aspose.words/comment/author/
---
## Comment.Author property

إرجاع أو تعيين اسم المؤلف للتعليق.

```csharp
public string Author { get; set; }
```

### ملاحظات

لا يمكن أن تكون لاغية.

الافتراضي هو سلسلة فارغة.

### أمثلة

يوضح كيفية طباعة كافة تعليقات المستند وردودهم.

```csharp
Document doc = new Document(MyDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

// إذا لم يكن للتعليق أصل ، فهو تعليق من "المستوى الأعلى" بدلاً من تعليق من نوع الرد.
// طباعة جميع تعليقات المستوى الأعلى مع أي ردود قد تكون لديهم.
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

### أنظر أيضا

* class [Comment](../)
* مساحة الاسم [Aspose.Words](../../comment/)
* المجسم [Aspose.Words](../../../)


