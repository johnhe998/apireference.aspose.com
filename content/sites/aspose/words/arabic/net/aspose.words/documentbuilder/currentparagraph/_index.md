---
title: DocumentBuilder.CurrentParagraph
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder ملكية. الحصول على الفقرة المحددة حاليًا في DocumentBuilder .
type: docs
weight: 50
url: /ar/net/aspose.words/documentbuilder/currentparagraph/
---
## DocumentBuilder.CurrentParagraph property

الحصول على الفقرة المحددة حاليًا في DocumentBuilder .

```csharp
public Paragraph CurrentParagraph { get; }
```

### ملاحظات

[`CurrentNode`](../currentnode/)

### أمثلة

يوضح كيفية نقل مؤشر منشئ المستندات إلى عقد مختلفة في المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إنشاء إشارة مرجعية صالحة ، كيان يتكون من عقد محاطة بعقدة بدء إشارة مرجعية ،
 // وعقدة نهاية مرجعية.
builder.StartBookmark("MyBookmark");
builder.Write("Bookmark contents.");
builder.EndBookmark("MyBookmark");

NodeCollection firstParagraphNodes = doc.FirstSection.Body.FirstParagraph.ChildNodes;

Assert.AreEqual(NodeType.BookmarkStart, firstParagraphNodes[0].NodeType);
Assert.AreEqual(NodeType.Run, firstParagraphNodes[1].NodeType);
Assert.AreEqual("Bookmark contents.", firstParagraphNodes[1].GetText().Trim());
Assert.AreEqual(NodeType.BookmarkEnd, firstParagraphNodes[2].NodeType);

// دائمًا ما يكون مؤشر منشئ المستندات متقدمًا على العقدة التي أضفناها بها آخر مرة.
// إذا كان مؤشر المنشئ في نهاية المستند ، فستكون العقدة الحالية خالية.
// العقدة السابقة هي نقطة نهاية الإشارة المرجعية التي أضفناها آخر مرة.
// ستؤدي إضافة عقد جديدة مع المنشئ إلى إلحاقها بالعقدة الأخيرة.
Assert.Null(builder.CurrentNode);

// إذا كنا نرغب في تحرير جزء مختلف من المستند باستخدام المنشئ ،
// سنحتاج إلى إحضار مؤشرها إلى العقدة التي نرغب في تعديلها.
builder.MoveToBookmark("MyBookmark");

// سيؤدي نقله إلى إشارة مرجعية إلى نقله إلى العقدة الأولى داخل عقد بداية ونهاية الإشارة المرجعية ، المسار المغلق.
Assert.AreEqual(firstParagraphNodes[1], builder.CurrentNode);

// يمكننا أيضًا تحريك المؤشر إلى عقدة فردية مثل هذه.
builder.MoveTo(doc.FirstSection.Body.FirstParagraph.GetChildNodes(NodeType.Any, false)[0]);

Assert.AreEqual(NodeType.BookmarkStart, builder.CurrentNode.NodeType);
Assert.AreEqual(doc.FirstSection.Body.FirstParagraph, builder.CurrentParagraph);
Assert.IsTrue(builder.IsAtStartOfParagraph);

// يمكننا استخدام طرق محددة للانتقال إلى بداية / نهاية المستند.
builder.MoveToDocumentEnd();

Assert.IsTrue(builder.IsAtEndOfParagraph);

builder.MoveToDocumentStart();

Assert.IsTrue(builder.IsAtStartOfParagraph);
```

### أنظر أيضا

* class [Paragraph](../../paragraph/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


