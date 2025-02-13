---
title: InlineStory.FirstParagraph
second_title: Aspose.Words لمراجع .NET API
description: InlineStory ملكية. الحصول على الفقرة الأولى في القصة .
type: docs
weight: 10
url: /ar/net/aspose.words/inlinestory/firstparagraph/
---
## InlineStory.FirstParagraph property

الحصول على الفقرة الأولى في القصة .

```csharp
public Paragraph FirstParagraph { get; }
```

### أمثلة

يوضح كيفية إضافة تعليق إلى فقرة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Hello world!");

Comment comment = new Comment(doc, "John Doe", "JD", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);
builder.MoveTo(comment.AppendChild(new Paragraph(doc)));
builder.Write("Comment text.");

Assert.AreEqual(DateTime.Today, comment.DateTime);

// في Microsoft Word ، يمكننا النقر بزر الماوس الأيمن فوق هذا التعليق في نص المستند لتحريره أو الرد عليه. 
doc.Save(ArtifactsDir + "InlineStory.AddComment.docx");
```

يوضح كيفية إدراج الحواشي السفلية وتخصيصها.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أضف نصًا ، وقم بالإشارة إليه بحاشية سفلية. ستضع هذه الحاشية السفلية مرجعًا صغيرًا مرتفعًا
// علامة بعد النص الذي يشير إليه وإنشاء إدخال أسفل النص الأساسي الرئيسي في أسفل الصفحة.
// سيحتوي هذا الإدخال على العلامة المرجعية للحاشية السفلية والنص المرجعي ،
// التي سنمررها إلى طريقة "InsertFootnote" الخاصة بمنشئ المستندات.
builder.Write("Main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// إذا تم تعيين هذه الخاصية على "true" ، فإن العلامة المرجعية للحاشية السفلية الخاصة بنا
// سيكون فهرسها بين جميع الحواشي السفلية للقسم.
// هذه هي الحاشية الأولى ، لذا فإن العلامة المرجعية ستكون "1".
Assert.True(footnote.IsAuto);

// يمكننا نقل منشئ المستند داخل الحاشية السفلية لتحرير نصه المرجعي. 
builder.MoveTo(footnote.FirstParagraph);
builder.Write(" More text added by a DocumentBuilder.");
builder.MoveToDocumentEnd();

Assert.AreEqual("\u0002 Footnote text. More text added by a DocumentBuilder.", footnote.GetText().Trim());

builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// يمكننا تعيين علامة مرجعية مخصصة ستستخدمها الحاشية السفلية بدلاً من رقم الفهرس الخاص بها.
footnote.ReferenceMark = "RefMark";

Assert.False(footnote.IsAuto);

// ستظل الإشارة المرجعية مع تعيين علامة "IsAuto" على "صواب" تظهر فهرسها الحقيقي
// حتى إذا كانت الإشارات المرجعية السابقة تعرض علامات مرجعية مخصصة ، فإن العلامة المرجعية لهذه الإشارة المرجعية ستكون "3".
builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

Assert.True(footnote.IsAuto);

doc.Save(ArtifactsDir + "InlineStory.AddFootnote.docx");
```

### أنظر أيضا

* class [Paragraph](../../paragraph/)
* class [InlineStory](../)
* مساحة الاسم [Aspose.Words](../../inlinestory/)
* المجسم [Aspose.Words](../../../)


