---
title: Footnote.FootnoteType
second_title: Aspose.Words لمراجع .NET API
description: Footnote ملكية. إرجاع قيمة تحدد ما إذا كانت هذه حاشية سفلية أو تعليق ختامي.
type: docs
weight: 20
url: /ar/net/aspose.words.notes/footnote/footnotetype/
---
## Footnote.FootnoteType property

إرجاع قيمة تحدد ما إذا كانت هذه حاشية سفلية أو تعليق ختامي.

```csharp
public FootnoteType FootnoteType { get; }
```

### أمثلة

يظهر الفرق بين الحواشي السفلية والتعليقات الختامية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// فيما يلي طريقتان لإرفاق المراجع المرقمة بالنص. كلا هذين المرجعين سيضيف
// علامة مرجعية صغيرة مرتفعة في الموقع الذي نقوم بإدخالها.
// العلامة المرجعية ، بشكل افتراضي ، هي رقم فهرس المرجع بين جميع المراجع في المستند.
// سيقوم كل مرجع أيضًا بإنشاء إدخال ، والذي سيكون له نفس العلامة المرجعية الموجودة في النص الأساسي
// والنص المرجعي ، والذي سنقوم بتمريره إلى طريقة "InsertFootnote" الخاصة بمنشئ المستندات.
// 1 - حاشية سفلية ، سيظهر إدخالها في نفس الصفحة كنص يشير إليه:
builder.Write("Footnote referenced main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, 
    "Footnote text, will appear at the bottom of the page that contains the referenced text.");

// 2 - تعليق ختامي ، سيظهر إدخاله في نهاية المستند:
builder.Write("Endnote referenced main body text.");
Footnote endnote = builder.InsertFootnote(FootnoteType.Endnote, 
    "Endnote text, will appear at the very end of the document.");

builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(FootnoteType.Footnote, footnote.FootnoteType);
Assert.AreEqual(FootnoteType.Endnote, endnote.FootnoteType);

doc.Save(ArtifactsDir + "InlineStory.FootnoteEndnote.docx");
```

### أنظر أيضا

* enum [FootnoteType](../../footnotetype/)
* class [Footnote](../)
* مساحة الاسم [Aspose.Words.Notes](../../footnote/)
* المجسم [Aspose.Words](../../../)


