---
title: Node.ParentNode
second_title: Aspose.Words لمراجع .NET API
description: Node ملكية. الحصول على الأصل المباشر لهذه العقدة.
type: docs
weight: 60
url: /ar/net/aspose.words/node/parentnode/
---
## Node.ParentNode property

الحصول على الأصل المباشر لهذه العقدة.

```csharp
public CompositeNode ParentNode { get; }
```

### ملاحظات

إذا تم إنشاء عقدة للتو ولم تتم إضافتها بعد إلى الشجرة ، أو إذا تمت إزالتها من الشجرة ، فسيكون الأصل فارغًا.

### أمثلة

يوضح كيفية الوصول إلى العقدة الأصلية للعقدة.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;

// قم بإلحاق عقدة تشغيل فرعية بالفقرة الأولى من المستند.
Run run = new Run(doc, "Hello world!");
para.AppendChild(run);

// الفقرة هي العقدة الأصلية لعقدة التشغيل. يمكننا تتبع هذا النسب
// طوال الطريق إلى عقدة المستند ، والتي تمثل جذر شجرة عقدة المستند.
Assert.AreEqual(para, run.ParentNode);
Assert.AreEqual(doc.FirstSection.Body, para.ParentNode);
Assert.AreEqual(doc.FirstSection, doc.FirstSection.Body.ParentNode);
Assert.AreEqual(doc, doc.FirstSection.ParentNode);
```

يوضح كيفية إنشاء عقدة وتعيين المستند الخاص بها.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
para.AppendChild(new Run(doc, "Hello world!"));

// لم نلحق بعد هذه الفقرة كطفل بأي عقدة مركبة.
Assert.IsNull(para.ParentNode);

// إذا كانت العقدة هي نوع عقدة فرعية مناسب لعقدة مركبة أخرى ،
// يمكننا إرفاقه كطفل فقط إذا كان لكلتا العقدتين نفس مستند المالك.
// مستند المالك هو المستند الذي مررناه إلى مُنشئ العقدة.
// لم نرفق هذه الفقرة بالمستند ، لذا لا يحتوي المستند على نصه.
Assert.AreEqual(para.Document, doc);
Assert.AreEqual(string.Empty, doc.GetText().Trim());

// نظرًا لأن المستند يمتلك هذه الفقرة ، يمكننا تطبيق أحد أنماطه على محتويات الفقرة.
para.ParagraphFormat.Style = doc.Styles["Heading 1"];

// أضف هذه العقدة إلى المستند ، ثم تحقق من محتوياتها.
doc.FirstSection.Body.AppendChild(para);

Assert.AreEqual(doc.FirstSection.Body, para.ParentNode);
Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### أنظر أيضا

* class [CompositeNode](../../compositenode/)
* class [Node](../)
* مساحة الاسم [Aspose.Words](../../node/)
* المجسم [Aspose.Words](../../../)


