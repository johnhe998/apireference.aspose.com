---
title: Enum RevisionTextEffect
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Layout.RevisionTextEffect تعداد. يسمح بتحديد تأثير الزخرفة لمراجعات نص المستند.
type: docs
weight: 3200
url: /ar/net/aspose.words.layout/revisiontexteffect/
---
## RevisionTextEffect enumeration

يسمح بتحديد تأثير الزخرفة لمراجعات نص المستند.

```csharp
public enum RevisionTextEffect
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | المحتوى المنقح ليس له تأثيرات خاصة مطبقة. هذا يتوافق معNoHighlight . |
| Color | `1` | يتم تمييز المحتوى المنقح باللون فقط. |
| Bold | `2` | جعل المحتوى المنقح غامقًا وملونًا. |
| Italic | `3` | جعل المحتوى المنقح مائلًا وملونًا. |
| Underline | `4` | تم وضع خط تحت المحتوى المنقح وملون. |
| DoubleUnderline | `5` | يتم تسطير المحتوى المنقح بشكل مزدوج وملون. |
| StrikeThrough | `6` | يتم رسم المحتوى المنقح وتلوينه. |
| DoubleStrikeThrough | `7` | يتم تمييز المحتوى المنقح بضرب مزدوج ولون. |
| Hidden | `8` | المحتوى المنقح مخفي . |

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

* مساحة الاسم [Aspose.Words.Layout](../../aspose.words.layout/)
* المجسم [Aspose.Words](../../)


