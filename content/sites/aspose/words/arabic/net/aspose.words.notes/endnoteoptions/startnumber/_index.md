---
title: EndnoteOptions.StartNumber
second_title: Aspose.Words لمراجع .NET API
description: EndnoteOptions ملكية. يحدد رقم البداية أو الحرف لأول تعليقات ختامية مرقمة تلقائيًا.
type: docs
weight: 40
url: /ar/net/aspose.words.notes/endnoteoptions/startnumber/
---
## EndnoteOptions.StartNumber property

يحدد رقم البداية أو الحرف لأول تعليقات ختامية مرقمة تلقائيًا.

```csharp
public int StartNumber { get; set; }
```

### ملاحظات

هذه الخاصية لها تأثير فقط عندما[`RestartRule`](../restartrule/) مضبوطة على Continuous.

### أمثلة

يوضح كيفية تعيين رقم يبدأ عنده المستند عدد الحواشي السفلية / التعليقات الختامية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// الحواشي السفلية والتعليقات الختامية هي طريقة لإرفاق مرجع أو تعليق جانبي بالنص
// لا يتعارض مع انسياب النص الأساسي الرئيسي. 
// يؤدي إدراج حاشية سفلية / تعليق ختامي إلى إضافة رمز مرجعي صغير مرتفع
// في النص الأساسي الرئيسي حيث نقوم بإدخال الحاشية السفلية / التعليق الختامي.
// تقوم كل حاشية سفلية / تعليق ختامي أيضًا بإنشاء إدخال يتكون من رمز
// الذي يطابق رمز المرجع في النص الأساسي الرئيسي.
// النص المرجعي الذي نمرره إلى طريقة "InsertEndnote" لمنشئ المستندات.
// تظهر إدخالات الحاشية السفلية ، افتراضيًا ، في أسفل كل صفحة تحتوي على
// تظهر رموزها المرجعية والتعليقات الختامية في نهاية المستند.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");

builder.InsertParagraph();

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");

// افتراضيًا ، يكون الرمز المرجعي لكل حاشية سفلية وتعليق ختامي هو الفهرس الخاص بها
// بين جميع الحواشي السفلية / التعليقات الختامية للمستند. يحتفظ كل مستند بحسابات منفصلة
// للحواشي السفلية والتعليقات الختامية ، وكلاهما يبدأ عند 1.
Assert.AreEqual(1, doc.FootnoteOptions.StartNumber);
Assert.AreEqual(1, doc.EndnoteOptions.StartNumber);

// يمكننا استخدام خاصية "StartNumber" للحصول على المستند
// بدء عدد الحواشي السفلية أو التعليقات الختامية برقم مختلف.
doc.EndnoteOptions.NumberStyle = NumberStyle.Arabic;
doc.EndnoteOptions.StartNumber = 50;

doc.Save(ArtifactsDir + "InlineStory.StartNumber.docx");
```

### أنظر أيضا

* class [EndnoteOptions](../)
* مساحة الاسم [Aspose.Words.Notes](../../endnoteoptions/)
* المجسم [Aspose.Words](../../../)


