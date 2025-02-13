---
title: SectionCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: SectionCollection ملكية. استرداد قسم في الفهرس المحدد.
type: docs
weight: 10
url: /ar/net/aspose.words/sectioncollection/item/
---
## SectionCollection indexer

استرداد قسم في الفهرس المحدد.

```csharp
public Section this[int index] { get; }
```

| معامل | وصف |
| --- | --- |
| index | فهرس في قائمة الأقسام. |

### ملاحظات

المؤشر على أساس الصفر.

يُسمح بالفهارس السلبية وتشير إلى الوصول من الجزء الخلفي من المجموعة. على سبيل المثال -1 تعني العنصر الأخير ، -2 تعني العنصر الثاني قبل الأخير وهكذا.

إذا كان الفهرس أكبر من أو يساوي عدد العناصر في القائمة ، فسيُرجع هذا مرجعًا فارغًا.

إذا كان الفهرس سالبًا وكانت قيمته المطلقة أكبر من عدد العناصر في القائمة ، فسيُرجع هذا مرجعًا فارغًا.

### أمثلة

يظهر وقت إعادة حساب تخطيط الصفحة للمستند.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// حفظ مستند إلى ملف PDF أو في صورة أو الطباعة لأول مرة سيتم تلقائيًا
// تخزين تخطيط المستند مؤقتًا داخل صفحاته.
doc.Save(ArtifactsDir + "Document.UpdatePageLayout.1.pdf");

// قم بتعديل المستند بطريقة ما.
doc.Styles["Normal"].Font.Size = 6;
doc.Sections[0].PageSetup.Orientation = Aspose.Words.Orientation.Landscape;

 // في الإصدار الحالي من Aspose.Words ، لا يؤدي تعديل المستند إلى إعادة البناء تلقائيًا
// تخطيط الصفحة المخبأة. إذا كنا نرغب في التخطيط المخبأ
// للبقاء محدثًا ، سنحتاج إلى تحديثه يدويًا.
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.UpdatePageLayout.2.pdf");
```

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

* class [Section](../../section/)
* class [SectionCollection](../)
* مساحة الاسم [Aspose.Words](../../sectioncollection/)
* المجسم [Aspose.Words](../../../)


