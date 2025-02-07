---
title: DocumentBuilder.MoveTo
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. لنقل المؤشر إلى عقدة سطرية أو إلى نهاية فقرة.
type: docs
weight: 460
url: /ar/net/aspose.words/documentbuilder/moveto/
---
## DocumentBuilder.MoveTo method

لنقل المؤشر إلى عقدة سطرية أو إلى نهاية فقرة.

```csharp
public void MoveTo(Node node)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| node | Node | يجب أن تكون العقدة فقرة أو فرعية مباشرة من فقرة. |

### ملاحظات

متيالعقدة هي عقدة مضمنة المستوى ، يتم نقل المؤشر إلى هذه العقدة وسيتم إدراج المزيد من المحتوى قبل تلك العقدة.

متيالعقدة هو **فقرة**، يتم نقل المؤشر إلى نهاية الفقرة وسيتم إدراج المزيد من المحتوى قبل فاصل الفقرة مباشرة.

متيالعقدةهي عقدة على مستوى الكتلة ولكنها ليست فقرة ، يتم نقل المؤشر إلى نهاية الفقرة الأولى إلى node على مستوى الكتلة وسيتم إدراج المزيد من المحتوى قبل فاصل الفقرة مباشرة.

### أمثلة

يوضح كيفية نقل موضع مؤشر DocumentBuilder إلى عقدة محددة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Run 1. ");

// يحتوي مُنشئ المستند على مؤشر يعمل كجزء من المستند
// حيث يقوم المنشئ بإلحاق عقد جديدة عندما نستخدم طرق إنشاء المستندات الخاصة به.
// يعمل هذا المؤشر بنفس طريقة عمل مؤشر Microsoft Word الوامض ،
// ودائمًا ما ينتهي به الأمر فورًا بعد أي عقدة قام المنشئ بإدراجها للتو.
// لإلحاق المحتوى بجزء مختلف من المستند ،
// يمكننا تحريك المؤشر إلى عقدة مختلفة باستخدام طريقة "MoveTo".
// يوجد المؤشر الآن أمام العقدة التي نقلناها إليها.
// ستؤدي إضافة تشغيل ثانٍ إلى إدراجه أمام التشغيل الأول.
builder.Writeln("Run 2. ");

Assert.AreEqual("Run 2. \rRun 1.", doc.GetText().Trim());

// حرك المؤشر إلى نهاية المستند لمتابعة إلحاق النص بالنهاية كما كان من قبل.
builder.MoveTo(doc.LastSection.Body.LastParagraph);
builder.Writeln("Run 3. ");

Assert.AreEqual("Run 2. \rRun 1. \rRun 3.", doc.GetText().Trim());
```

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

* class [Node](../../node/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


