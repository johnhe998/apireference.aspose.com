---
title: CommentCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: CommentCollection ملكية. يسترجع أ تعليق في الفهرس المحدد.
type: docs
weight: 10
url: /ar/net/aspose.words/commentcollection/item/
---
## CommentCollection indexer

يسترجع أ **تعليق** في الفهرس المحدد.

```csharp
public Comment this[int index] { get; }
```

| معامل | وصف |
| --- | --- |
| index | فهرس في المجموعة. |

### ملاحظات

المؤشر على أساس الصفر.

يُسمح بالفهارس السلبية وتشير إلى الوصول من الجزء الخلفي من المجموعة. على سبيل المثال -1 تعني العنصر الأخير ، -2 تعني العنصر الثاني قبل الأخير وهكذا.

إذا كان الفهرس أكبر من أو يساوي عدد العناصر في القائمة ، فسيُرجع هذا مرجعًا فارغًا.

إذا كان الفهرس سالبًا وكانت قيمته المطلقة أكبر من عدد العناصر في القائمة ، فسيُرجع هذا مرجعًا فارغًا.

### أمثلة

يوضح كيفية إزالة ردود التعليق.

```csharp
Document doc = new Document();

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");

doc.FirstSection.Body.FirstParagraph.AppendChild(comment);

comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "New reply");
comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "Another reply");

Assert.AreEqual(2, comment.Replies.Count()); 

// فيما يلي طريقتان لإزالة الردود من تعليق.
// 1 - استخدم طريقة "RemoveReply" لإزالة الردود من تعليق بشكل فردي:
comment.RemoveReply(comment.Replies[0]);

Assert.AreEqual(1, comment.Replies.Count());

// 2 - استخدم طريقة "RemoveAllReplies" لإزالة جميع الردود من تعليق مرة واحدة:
comment.RemoveAllReplies();

Assert.AreEqual(0, comment.Replies.Count());
```

### أنظر أيضا

* class [Comment](../../comment/)
* class [CommentCollection](../)
* مساحة الاسم [Aspose.Words](../../commentcollection/)
* المجسم [Aspose.Words](../../../)


