---
title: FindReplaceOptions.MatchCase
second_title: Aspose.Words لمراجع .NET API
description: FindReplaceOptions ملكية. يشير True إلى مقارنة حساسة لحالة الأحرف  بينما يشير الخطأ خطأ إلى مقارنة غير حساسة لحالة الأحرف.
type: docs
weight: 120
url: /ar/net/aspose.words.replacing/findreplaceoptions/matchcase/
---
## FindReplaceOptions.MatchCase property

يشير True إلى مقارنة حساسة لحالة الأحرف ، بينما يشير الخطأ "خطأ" إلى مقارنة غير حساسة لحالة الأحرف.

```csharp
public bool MatchCase { get; set; }
```

### أمثلة

يوضح كيفية تبديل حساسية حالة الأحرف عند إجراء عملية البحث والاستبدال.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Ruby bought a ruby necklace.");

// يمكننا استخدام كائن "FindReplaceOptions" لتعديل عملية البحث والاستبدال.
FindReplaceOptions options = new FindReplaceOptions();

// اضبط علامة "MatchCase" على "true" لتطبيق حساسية حالة الأحرف أثناء البحث عن سلاسل لاستبدالها.
// اضبط علامة "MatchCase" على "خطأ" لتجاهل حالة الأحرف أثناء البحث عن نص لاستبداله.
options.MatchCase = matchCase;

doc.Range.Replace("Ruby", "Jade", options);

Assert.AreEqual(matchCase ? "Jade bought a ruby necklace." : "Jade bought a Jade necklace.",
    doc.GetText().Trim());
```

### أنظر أيضا

* class [FindReplaceOptions](../)
* مساحة الاسم [Aspose.Words.Replacing](../../findreplaceoptions/)
* المجسم [Aspose.Words](../../../)


