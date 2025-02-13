---
title: HeaderFooter.HeaderFooter
second_title: Aspose.Words لمراجع .NET API
description: HeaderFooter البناء. إنشاء رأس أو تذييل جديد من النوع المحدد.
type: docs
weight: 10
url: /ar/net/aspose.words/headerfooter/headerfooter/
---
## HeaderFooter constructor

إنشاء رأس أو تذييل جديد من النوع المحدد.

```csharp
public HeaderFooter(DocumentBase doc, HeaderFooterType headerFooterType)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| doc | DocumentBase | وثيقة المالك. |
| headerFooterType | HeaderFooterType | أ[`HeaderFooterType`](../headerfootertype/)value التي تحدد نوع الرأس أو التذييل. |

### ملاحظات

متي **تذييل الرأس** تم إنشاؤه ، فهو ينتمي إلى المستند المحدد ، ولكنه ليس بعد جزءًا من المستند و **عقدة الأم** باطل.

لإلحاق **تذييل الرأس** إلى أ **الجزء** استخدم Section.InsertAfter، Section.InsertBefore، HeadersFooters.Add أو HeadersFooters.Insert.

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

* class [DocumentBase](../../documentbase/)
* enum [HeaderFooterType](../../headerfootertype/)
* class [HeaderFooter](../)
* مساحة الاسم [Aspose.Words](../../headerfooter/)
* المجسم [Aspose.Words](../../../)


