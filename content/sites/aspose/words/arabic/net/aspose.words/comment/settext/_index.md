---
title: Comment.SetText
second_title: Aspose.Words لمراجع .NET API
description: Comment طريقة. هذه طريقة ملائمة تسمح لك بتعيين نص التعليق بسهولة.
type: docs
weight: 150
url: /ar/net/aspose.words/comment/settext/
---
## Comment.SetText method

هذه طريقة ملائمة تسمح لك بتعيين نص التعليق بسهولة.

```csharp
public void SetText(string text)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| text | String | النص الجديد للتعليق. |

### ملاحظات

تسمح هذه الطريقة بتعيين نص التعليق بسرعة من سلسلة. يمكن أن تحتوي السلسلة على فواصل فقرات ، سيؤدي ذلك إلى إنشاء فقرات نصية في التعليق وفقًا لذلك. إلى إنشاء نص التعليق.

### أمثلة

يوضح كيفية إضافة تعليق إلى مستند ، ثم الرد عليه.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");

// ضع التعليق في عقدة في نص المستند.
// سيظهر هذا التعليق في موقع فقرته ،
// خارج هامش الجانب الأيمن للصفحة ، وبخط منقط يربطها بالفقرة الخاصة بها.
builder.CurrentParagraph.AppendChild(comment);

// أضف ردًا ، والذي سيظهر تحت التعليق الأصلي.
comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "New reply");

// التعليقات والردود كلاهما عقد تعليق.
Assert.AreEqual(2, doc.GetChildNodes(NodeType.Comment, true).Count);

// التعليقات التي لا ترد على التعليقات الأخرى هي "عالية المستوى". ليس لديهم تعليقات أسلاف.
Assert.Null(comment.Ancestor);

// تحتوي الردود على تعليق من مستوى أعلى من سلف.
Assert.AreEqual(comment, comment.Replies[0].Ancestor);

doc.Save(ArtifactsDir + "Comment.AddCommentWithReply.docx");
```

### أنظر أيضا

* class [Comment](../)
* مساحة الاسم [Aspose.Words](../../comment/)
* المجسم [Aspose.Words](../../../)


