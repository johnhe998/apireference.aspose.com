---
title: FindReplaceOptions.IgnoreFootnotes
second_title: Aspose.Words لمراجع .NET API
description: FindReplaceOptions ملكية. الحصول على أو تعيين قيمة منطقية تشير إما إلى تجاهل الحواشي السفلية . القيمة الافتراضية هيخاطئة .
type: docs
weight: 90
url: /ar/net/aspose.words.replacing/findreplaceoptions/ignorefootnotes/
---
## FindReplaceOptions.IgnoreFootnotes property

الحصول على أو تعيين قيمة منطقية تشير إما إلى تجاهل الحواشي السفلية . القيمة الافتراضية هي`خاطئة` .

```csharp
public bool IgnoreFootnotes { get; set; }
```

### أمثلة

يوضح كيفية تجاهل الحواشي السفلية أثناء عملية البحث والاستبدال.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
builder.InsertFootnote(FootnoteType.Footnote, "Lorem ipsum dolor sit amet, consectetur adipiscing elit.");

builder.InsertParagraph();

builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
builder.InsertFootnote(FootnoteType.Endnote, "Lorem ipsum dolor sit amet, consectetur adipiscing elit.");

// اضبط علامة "IgnoreFootnotes" على "true" للحصول على البحث والاستبدال
// لتجاهل النص داخل الحواشي السفلية.
// اضبط علامة "IgnoreFootnotes" على "خطأ" للحصول على البحث والاستبدال
// العملية للبحث أيضًا عن نص داخل الحواشي السفلية.
FindReplaceOptions options = new FindReplaceOptions { IgnoreFootnotes = isIgnoreFootnotes };
doc.Range.Replace("Lorem ipsum", "Replaced Lorem ipsum", options);
```

### أنظر أيضا

* class [FindReplaceOptions](../)
* مساحة الاسم [Aspose.Words.Replacing](../../findreplaceoptions/)
* المجسم [Aspose.Words](../../../)


