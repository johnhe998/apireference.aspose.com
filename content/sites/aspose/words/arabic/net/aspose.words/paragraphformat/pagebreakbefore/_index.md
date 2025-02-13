---
title: ParagraphFormat.PageBreakBefore
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. True إذا تم فرض فاصل صفحة قبل الفقرة.
type: docs
weight: 250
url: /ar/net/aspose.words/paragraphformat/pagebreakbefore/
---
## ParagraphFormat.PageBreakBefore property

True إذا تم فرض فاصل صفحة قبل الفقرة.

```csharp
public bool PageBreakBefore { get; set; }
```

### أمثلة

يوضح كيفية إنشاء فقرات مع فواصل الصفحات في البداية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// اضبط هذه العلامة على "صواب" لتطبيق فاصل صفحة على بداية كل فقرة
// الذي سيُنشئه مُنشئ المستند ضمن تكوين تنسيق الفقرة هذا.
// لن تتلقى الفقرة الأولى فاصل صفحات.
// اترك هذه العلامة على أنها "خطأ" لبدء كل فقرة جديدة في نفس الصفحة
// كالسابق ، بشرط وجود مساحة كافية.
builder.ParagraphFormat.PageBreakBefore = pageBreakBefore;

builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

LayoutCollector layoutCollector = new LayoutCollector(doc);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

if (pageBreakBefore)
{
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[0]));
    Assert.AreEqual(2, layoutCollector.GetStartPageIndex(paragraphs[1]));
}
else
{
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[0]));
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[1]));
}

doc.Save(ArtifactsDir + "ParagraphFormat.PageBreakBefore.docx");
```

### أنظر أيضا

* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


