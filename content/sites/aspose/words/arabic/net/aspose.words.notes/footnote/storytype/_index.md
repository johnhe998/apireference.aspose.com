---
title: Footnote.StoryType
second_title: Aspose.Words لمراجع .NET API
description: Footnote ملكية. عوائد نوع القصة أو نوع القصة .
type: docs
weight: 60
url: /ar/net/aspose.words.notes/footnote/storytype/
---
## Footnote.StoryType property

عوائد **نوع القصة** أو **نوع القصة** .

```csharp
public override StoryType StoryType { get; }
```

### أمثلة

يوضح كيفية إدراج عقد InlineStory.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, null);

// تحتوي عقد الجدول على طريقة "WarrantyMinimum ()" التي تتأكد من احتواء الجدول على خلية واحدة على الأقل.
Table table = new Table(doc);
table.EnsureMinimum();

// يمكننا وضع جدول داخل حاشية سفلية ، مما يجعلها تظهر في تذييل الصفحة المرجعية.
Assert.That(footnote.Tables, Is.Empty);
footnote.AppendChild(table);
Assert.AreEqual(1, footnote.Tables.Count);
Assert.AreEqual(NodeType.Table, footnote.LastChild.NodeType);

// يحتوي InlineStory على طريقة "WarrantyMinimum ()" أيضًا ، ولكن في هذه الحالة ،
// يتأكد من أن الطفل الأخير في العقدة عبارة عن فقرة ،
// حتى نتمكن من النقر وكتابة النص بسهولة في Microsoft Word.
footnote.EnsureMinimum();
Assert.AreEqual(NodeType.Paragraph, footnote.LastChild.NodeType);

// تحرير مظهر الارتساء ، وهو رقم مرتفع صغير
// في النص الرئيسي الذي يشير إلى الحاشية السفلية.
footnote.Font.Name = "Arial";
footnote.Font.Color = Color.Green;

// كل عقد القصة المضمنة لها أنواع القصة الخاصة بها.
Assert.AreEqual(StoryType.Footnotes, footnote.StoryType);

// التعليق هو نوع آخر من القصص المضمنة.
Comment comment = (Comment)builder.CurrentParagraph.AppendChild(new Comment(doc, "John Doe", "J. D.", DateTime.Now));

// ستكون الفقرة الأصلية لعقدة المجموعة النصية المضمنة هي الفقرة من نص المستند الأساسي.
Assert.AreEqual(doc.FirstSection.Body.FirstParagraph, comment.ParentParagraph);

// ومع ذلك ، فإن الفقرة الأخيرة هي تلك الموجودة في محتويات نص التعليق ،
// والتي ستكون خارج نص المستند الأساسي في فقاعة كلامية.
// لن يحتوي التعليق على أي عقد فرعية بشكل افتراضي ،
// حتى نتمكن من تطبيق طريقة WarrantyMinimum () لوضع فقرة هنا أيضًا.
Assert.Null(comment.LastParagraph);
comment.EnsureMinimum();
Assert.AreEqual(NodeType.Paragraph, comment.LastChild.NodeType);

// بمجرد الحصول على فقرة ، يمكننا تحريك المنشئ للقيام بذلك وكتابة تعليقنا.
builder.MoveTo(comment.LastParagraph);
builder.Write("My comment.");

Assert.AreEqual(StoryType.Comments, comment.StoryType);

doc.Save(ArtifactsDir + "InlineStory.InsertInlineStoryNodes.docx");
```

### أنظر أيضا

* enum [StoryType](../../../aspose.words/storytype/)
* class [Footnote](../)
* مساحة الاسم [Aspose.Words.Notes](../../footnote/)
* المجسم [Aspose.Words](../../../)


