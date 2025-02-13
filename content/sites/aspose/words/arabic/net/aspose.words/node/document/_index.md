---
title: Node.Document
second_title: Aspose.Words لمراجع .NET API
description: Node ملكية. الحصول على المستند الذي تنتمي إليه هذه العقدة .
type: docs
weight: 20
url: /ar/net/aspose.words/node/document/
---
## Node.Document property

الحصول على المستند الذي تنتمي إليه هذه العقدة .

```csharp
public virtual DocumentBase Document { get; }
```

### ملاحظات

تنتمي العقدة دائمًا إلى مستند حتى لو تم إنشاؤه للتو ولم يتم إضافته بعد إلى الشجرة ، أو إذا تمت إزالته من الشجرة.

### أمثلة

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

* class [DocumentBase](../../documentbase/)
* class [Node](../)
* مساحة الاسم [Aspose.Words](../../node/)
* المجسم [Aspose.Words](../../../)


