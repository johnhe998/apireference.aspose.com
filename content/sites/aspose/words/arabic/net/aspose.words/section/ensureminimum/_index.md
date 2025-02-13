---
title: Section.EnsureMinimum
second_title: Aspose.Words لمراجع .NET API
description: Section طريقة. يضمن أن القسم به نص فقرة واحدة.
type: docs
weight: 130
url: /ar/net/aspose.words/section/ensureminimum/
---
## Section.EnsureMinimum method

يضمن أن القسم به نص فقرة واحدة.

```csharp
public void EnsureMinimum()
```

### أمثلة

يوضح كيفية تحضير عقدة قسم جديدة للتحرير.

```csharp
Document doc = new Document();

// يأتي المستند الفارغ مع قسم يحتوي على نص ، والذي بدوره يحتوي على فقرة.
// يمكننا إضافة محتويات إلى هذا المستند عن طريق إضافة عناصر مثل عمليات تشغيل النص أو الأشكال أو الجداول إلى تلك الفقرة.
Assert.AreEqual(NodeType.Section, doc.GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Body, doc.Sections[0].GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Paragraph, doc.Sections[0].Body.GetChild(NodeType.Any, 0, true).NodeType);

// إذا أضفنا قسمًا جديدًا مثل هذا ، فلن يحتوي على جسم ، أو أي عقد فرعية أخرى.
doc.Sections.Add(new Section(doc));

Assert.AreEqual(0, doc.Sections[1].GetChildNodes(NodeType.Any, true).Count);

// قم بتشغيل طريقة "ضمان الحد الأدنى" لإضافة نص وفقرة إلى هذا القسم لبدء تحريره.
doc.LastSection.EnsureMinimum();

Assert.AreEqual(NodeType.Body, doc.Sections[1].GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Paragraph, doc.Sections[1].Body.GetChild(NodeType.Any, 0, true).NodeType);

doc.Sections[0].Body.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### أنظر أيضا

* class [Section](../)
* مساحة الاسم [Aspose.Words](../../section/)
* المجسم [Aspose.Words](../../../)


