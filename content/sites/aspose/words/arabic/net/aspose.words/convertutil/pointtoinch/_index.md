---
title: ConvertUtil.PointToInch
second_title: Aspose.Words لمراجع .NET API
description: ConvertUtil طريقة. تحويل النقاط إلى بوصة .
type: docs
weight: 50
url: /ar/net/aspose.words/convertutil/pointtoinch/
---
## ConvertUtil.PointToInch method

تحويل النقاط إلى بوصة .

```csharp
public static double PointToInch(double points)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| points | Double | القيمة المطلوب تحويلها. |

### ملاحظات

1 بوصة تساوي 72 نقطة .

### أمثلة

يوضح كيفية تحديد خصائص الصفحة بالبوصة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يحدد "إعداد الصفحة" في القسم حجم هوامش الصفحة بالنقاط.
// يمكننا أيضًا استخدام فئة "ConvertUtil" لاستخدام وحدة قياس أكثر شيوعًا ،
// مثل البوصة عند تحديد الحدود.
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(2.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(2.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);

// البوصة 72 نقطة.
Assert.AreEqual(72.0d, ConvertUtil.InchToPoint(1));
Assert.AreEqual(1.0d, ConvertUtil.PointToInch(72));

// أضف محتوى لتوضيح الهوامش الجديدة.
builder.Writeln($"This Text is {pageSetup.LeftMargin} points/{ConvertUtil.PointToInch(pageSetup.LeftMargin)} inches from the left, " +
                $"{pageSetup.RightMargin} points/{ConvertUtil.PointToInch(pageSetup.RightMargin)} inches from the right, " +
                $"{pageSetup.TopMargin} points/{ConvertUtil.PointToInch(pageSetup.TopMargin)} inches from the top, " +
                $"and {pageSetup.BottomMargin} points/{ConvertUtil.PointToInch(pageSetup.BottomMargin)} inches from the bottom of the page.");

doc.Save(ArtifactsDir + "UtilityClasses.PointsAndInches.docx");
```

### أنظر أيضا

* class [ConvertUtil](../)
* مساحة الاسم [Aspose.Words](../../convertutil/)
* المجسم [Aspose.Words](../../../)


