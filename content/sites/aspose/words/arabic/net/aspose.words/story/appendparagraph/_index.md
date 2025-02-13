---
title: Story.AppendParagraph
second_title: Aspose.Words لمراجع .NET API
description: Story طريقة. طريقة اختصار تنشئ ملفParagraph كائن مع نص اختياري وإلحاقه بنهاية هذا الكائن.
type: docs
weight: 60
url: /ar/net/aspose.words/story/appendparagraph/
---
## Story.AppendParagraph method

طريقة اختصار تنشئ ملف[`Paragraph`](../../paragraph/) كائن مع نص اختياري وإلحاقه بنهاية هذا الكائن.

```csharp
public Paragraph AppendParagraph(string text)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| text | String | نص الفقرة. يمكن أن تكون سلسلة فارغة أو فارغة. |

### قيمة الإرجاع

الفقرة التي تم إنشاؤها وإلحاقها حديثًا.

### أمثلة

يوضح كيفية إنشاء رأس وتذييل.

```csharp
Document doc = new Document();

// إنشاء رأس وإلحاق فقرة به. النص في تلك الفقرة
// في أعلى كل صفحة من هذا القسم ، فوق النص الأساسي الرئيسي.
HeaderFooter header = new HeaderFooter(doc, HeaderFooterType.HeaderPrimary);
doc.FirstSection.HeadersFooters.Add(header);

Paragraph para = header.AppendParagraph("My header.");

Assert.True(header.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

// إنشاء تذييل وإلحاق فقرة به. النص في تلك الفقرة
// في أسفل كل صفحة من هذا القسم ، أسفل النص الأساسي الرئيسي.
HeaderFooter footer = new HeaderFooter(doc, HeaderFooterType.FooterPrimary);
doc.FirstSection.HeadersFooters.Add(footer);

para = footer.AppendParagraph("My footer.");

Assert.False(footer.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

Assert.AreEqual(footer, para.ParentStory);
Assert.AreEqual(footer.ParentSection, para.ParentSection);
Assert.AreEqual(footer.ParentSection, header.ParentSection);

doc.Save(ArtifactsDir + "HeaderFooter.Create.docx");
```

### أنظر أيضا

* class [Paragraph](../../paragraph/)
* class [Story](../)
* مساحة الاسم [Aspose.Words](../../story/)
* المجسم [Aspose.Words](../../../)


