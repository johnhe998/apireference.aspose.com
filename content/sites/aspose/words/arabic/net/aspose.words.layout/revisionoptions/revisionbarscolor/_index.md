---
title: RevisionOptions.RevisionBarsColor
second_title: Aspose.Words لمراجع .NET API
description: RevisionOptions ملكية. يسمح بتحديد اللون الذي سيتم استخدامه للأشرطة الجانبية التي تحدد أسطر المستند التي تحتوي على معلومات منقحة. القيمة الافتراضية هيRed .
type: docs
weight: 130
url: /ar/net/aspose.words.layout/revisionoptions/revisionbarscolor/
---
## RevisionOptions.RevisionBarsColor property

يسمح بتحديد اللون الذي سيتم استخدامه للأشرطة الجانبية التي تحدد أسطر المستند التي تحتوي على معلومات منقحة. القيمة الافتراضية هيRed .

```csharp
public RevisionColor RevisionBarsColor { get; set; }
```

### ملاحظات

تعيين هذه الخاصية إلىByAuthor أوNoHighlight القيم ستؤدي إلى إخفاء أشرطة المراجعة من التخطيط.

### أمثلة

يوضح كيفية تعديل مظهر المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// احصل على كائن RevisionOptions الذي يتحكم في مظهر المراجعات.
RevisionOptions revisionOptions = doc.LayoutOptions.RevisionOptions;

// تقديم مراجعات الإدراج باللونين الأخضر والمائل.
revisionOptions.InsertedTextColor = RevisionColor.Green;
revisionOptions.InsertedTextEffect = RevisionTextEffect.Italic;

// تقديم مراجعات الحذف باللون الأحمر والعريض.
revisionOptions.DeletedTextColor = RevisionColor.Red;
revisionOptions.DeletedTextEffect = RevisionTextEffect.Bold;

// سيظهر النص نفسه مرتين في مراجعة الحركة:
// مرة في نقطة المغادرة ومرة في وجهة الوصول.
// جعل النص في النسخة المنقولة أصفر بخط مزدوج من خلاله
// والأزرق مزدوج تحته خط في المراجعة المنقولة إلى.
revisionOptions.MovedFromTextColor = RevisionColor.Yellow;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleStrikeThrough;
revisionOptions.MovedToTextColor = RevisionColor.Blue;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleUnderline;

// تقديم تنقيحات التنسيق باللون الأحمر الداكن والجريء.
revisionOptions.RevisedPropertiesColor = RevisionColor.DarkRed;
revisionOptions.RevisedPropertiesEffect = RevisionTextEffect.Bold;

// ضع شريطًا سميكًا أزرق داكن على الجانب الأيسر من الصفحة بجوار الأسطر المتأثرة بالمراجعات.
revisionOptions.RevisionBarsColor = RevisionColor.DarkBlue;
revisionOptions.RevisionBarsWidth = 15.0f;

// إظهار علامات المراجعة والنص الأصلي.
revisionOptions.ShowOriginalRevision = true;
revisionOptions.ShowRevisionMarks = true;

// احصل على الحركة والحذف وتنسيق المراجعات والتعليقات لتظهر في بالونات خضراء
// على الجانب الأيمن من الصفحة.
revisionOptions.ShowInBalloons = ShowInBalloons.Format;
revisionOptions.CommentColor = RevisionColor.BrightGreen;

// هذه الميزات قابلة للتطبيق فقط على تنسيقات مثل .pdf أو .jpg.
doc.Save(ArtifactsDir + "Revision.RevisionOptions.pdf");
```

### أنظر أيضا

* enum [RevisionColor](../../revisioncolor/)
* class [RevisionOptions](../)
* مساحة الاسم [Aspose.Words.Layout](../../revisionoptions/)
* المجسم [Aspose.Words](../../../)


