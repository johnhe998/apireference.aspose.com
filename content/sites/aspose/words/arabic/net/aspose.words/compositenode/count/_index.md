---
title: CompositeNode.Count
second_title: Aspose.Words لمراجع .NET API
description: CompositeNode ملكية. الحصول على عدد الأطفال المباشرين لهذه العقدة.
type: docs
weight: 20
url: /ar/net/aspose.words/compositenode/count/
---
## CompositeNode.Count property

الحصول على عدد الأطفال المباشرين لهذه العقدة.

```csharp
public int Count { get; }
```

### أمثلة

يوضح كيفية إضافة وتحديث وحذف العقد الفرعية في مجموعة العناصر الفرعية الخاصة بالعقدة المركبة.

```csharp
Document doc = new Document();

// يحتوي المستند الفارغ ، افتراضيًا ، على فقرة واحدة.
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);

// يمكن أن تحتوي العقد المركبة مثل فقرتنا على عقد مركبة ومضمنة أخرى مثل الأطفال.
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Run paragraphText = new Run(doc, "Initial text. ");
paragraph.AppendChild(paragraphText);

// إنشاء ثلاث عقد تشغيل أخرى.
Run run1 = new Run(doc, "Run 1. ");
Run run2 = new Run(doc, "Run 2. ");
Run run3 = new Run(doc, "Run 3. ");

// لن يعرض نص المستند عمليات التشغيل هذه حتى نقوم بإدخالها في عقدة مركبة
// هذا بحد ذاته جزء من شجرة عقدة المستند ، كما فعلنا مع التشغيل الأول.
// يمكننا تحديد مكان محتويات نص العقد التي ندرجها
// في المستند عن طريق تحديد موقع الإدراج المتعلق بعقدة أخرى في الفقرة.
Assert.AreEqual("Initial text.", paragraph.GetText().Trim());

// أدخل المدى الثاني في الفقرة أمام التشغيل الأولي.
paragraph.InsertBefore(run2, paragraphText);

Assert.AreEqual("Run 2. Initial text.", paragraph.GetText().Trim());

// أدخل الجولة الثالثة بعد التشغيل الأولي.
paragraph.InsertAfter(run3, paragraphText);

Assert.AreEqual("Run 2. Initial text. Run 3.", paragraph.GetText().Trim());

// أدخل التشغيل الأول في بداية مجموعة العقد الفرعية للفقرة.
paragraph.PrependChild(run1);

Assert.AreEqual("Run 1. Run 2. Initial text. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(4, paragraph.GetChildNodes(NodeType.Any, true).Count);

// يمكننا تعديل محتويات التشغيل عن طريق تحرير وحذف العقد الفرعية الموجودة.
((Run)paragraph.GetChildNodes(NodeType.Run, true)[1]).Text = "Updated run 2. ";
paragraph.GetChildNodes(NodeType.Run, true).Remove(paragraphText);

Assert.AreEqual("Run 1. Updated run 2. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(3, paragraph.GetChildNodes(NodeType.Any, true).Count);
```

### أنظر أيضا

* class [CompositeNode](../)
* مساحة الاسم [Aspose.Words](../../compositenode/)
* المجسم [Aspose.Words](../../../)


