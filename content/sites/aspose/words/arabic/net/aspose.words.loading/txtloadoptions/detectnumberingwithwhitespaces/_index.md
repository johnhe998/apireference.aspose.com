---
title: TxtLoadOptions.DetectNumberingWithWhitespaces
second_title: Aspose.Words لمراجع .NET API
description: TxtLoadOptions ملكية. يسمح بتحديد كيفية التعرف على عناصر القائمة المرقمة عند استيراد المستند من تنسيق نص عادي. القيمة الافتراضية هي true.
type: docs
weight: 20
url: /ar/net/aspose.words.loading/txtloadoptions/detectnumberingwithwhitespaces/
---
## TxtLoadOptions.DetectNumberingWithWhitespaces property

يسمح بتحديد كيفية التعرف على عناصر القائمة المرقمة عند استيراد المستند من تنسيق نص عادي. القيمة الافتراضية هي true.

```csharp
public bool DetectNumberingWithWhitespaces { get; set; }
```

### ملاحظات

إذا تم تعيين هذا الخيار على "خطأ" ، فإن خوارزمية التعرف على القوائم تكتشف فقرات القائمة ، عندما تنتهي أرقام القائمة بـ إما نقطة أو قوس أيمن أو رموز نقطية (مثل "•" أو "*" أو "-" أو "س").

إذا تم تعيين هذا الخيار على "صحيح" ، يتم استخدام المسافات البيضاء أيضًا كمحددات لأرقام القائمة: خوارزمية التعرف على القائمة لترقيم النمط العربي (1. ، 1.1.2.) تستخدم كل من المسافات البيضاء والرموز النقطية (".").

### أمثلة

يوضح كيفية اكتشاف القوائم عند تحميل مستندات نص عادي.

```csharp
// قم بإنشاء مستند نص عادي في سلسلة مكونة من أربعة أجزاء منفصلة قد نفسر كقوائم ،
// مع محددات مختلفة. عند تحميل مستند النص العادي في كائن "مستند" ،
// Aspose.Words ستكتشف دائمًا القوائم الثلاث الأولى وستضيف كائن "قائمة"
// لكل من خاصية "القوائم" الخاصة بالمستند.
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";

// قم بإنشاء كائن "TxtLoadOptions" ، والذي يمكننا تمريره إلى مُنشئ المستند
// لتعديل كيفية تحميل مستند نص عادي.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// اضبط خاصية "DetectNumberingWithWhitespaces" على "true" لاكتشاف العناصر المرقمة
// مع محددات المسافات ، مثل القائمة الرابعة في وثيقتنا ، كقوائم.
// قد يكتشف هذا أيضًا بشكل خاطئ الفقرات التي تبدأ بالأرقام كقوائم.
// تعيين خاصية "DetectNumberingWithWhitespaces" على "false"
// لعدم إنشاء قوائم من عناصر مرقمة بمحددات مسافات بيضاء.
loadOptions.DetectNumberingWithWhitespaces = detectNumberingWithWhitespaces;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

if (detectNumberingWithWhitespaces)
{
    Assert.AreEqual(4, doc.Lists.Count);
    Assert.True(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
else
{
    Assert.AreEqual(3, doc.Lists.Count);
    Assert.False(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
```

### أنظر أيضا

* class [TxtLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../txtloadoptions/)
* المجسم [Aspose.Words](../../../)


