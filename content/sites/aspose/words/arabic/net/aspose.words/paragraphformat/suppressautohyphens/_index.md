---
title: ParagraphFormat.SuppressAutoHyphens
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. يحدد ما إذا كان يجب استثناء الفقرة الحالية من أي واصلة والتي يتم تطبيقها في إعدادات المستند.
type: docs
weight: 360
url: /ar/net/aspose.words/paragraphformat/suppressautohyphens/
---
## ParagraphFormat.SuppressAutoHyphens property

يحدد ما إذا كان يجب استثناء الفقرة الحالية من أي واصلة والتي يتم تطبيقها في إعدادات المستند.

```csharp
public bool SuppressAutoHyphens { get; set; }
```

### أمثلة

يوضح كيفية منع الواصلة في فقرة.

```csharp
Hyphenation.RegisterDictionary("de-CH", MyDir + "hyph_de_CH.dic");

Assert.True(Hyphenation.IsDictionaryRegistered("de-CH"));

// افتح مستندًا يحتوي على نص بلغة تطابق لغة قاموسنا.
// عندما نحفظ هذا المستند بتنسيق حفظ صفحة ثابت ، سيكون لنصه واصلة.
Document doc = new Document(MyDir + "German text.docx");

// يمكننا تعيين خاصية "SuppressAutoHyphens" على "true" لتعطيل الواصلة
// لفقرة معينة مع إبقائها ممكّنة لبقية المستند.
// القيمة الافتراضية لهذه الخاصية هي "خطأ" ،
// مما يعني أن كل فقرة بشكل افتراضي تستخدم الواصلة إن وجدت.
doc.FirstSection.Body.FirstParagraph.ParagraphFormat.SuppressAutoHyphens = suppressAutoHyphens;

doc.Save(ArtifactsDir + "ParagraphFormat.SuppressHyphens.pdf");
```

### أنظر أيضا

* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


