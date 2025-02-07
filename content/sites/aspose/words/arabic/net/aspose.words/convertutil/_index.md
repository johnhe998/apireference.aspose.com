---
title: Class ConvertUtil
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.ConvertUtil فصل. يوفر وظائف مساعدة للتحويل بين وحدات القياس المختلفة.
type: docs
weight: 350
url: /ar/net/aspose.words/convertutil/
---
## ConvertUtil class

يوفر وظائف مساعدة للتحويل بين وحدات القياس المختلفة.

```csharp
public static class ConvertUtil
```

## طُرق

| اسم | وصف |
| --- | --- |
| static [InchToPoint](../../aspose.words/convertutil/inchtopoint/)(double) | تحويل بوصة إلى نقاط . |
| static [MillimeterToPoint](../../aspose.words/convertutil/millimetertopoint/)(double) | تحويل المليمترات إلى نقاط . |
| static [PixelToNewDpi](../../aspose.words/convertutil/pixeltonewdpi/)(double, double, double) | يحول البكسل من دقة إلى أخرى. |
| static [PixelToPoint](../../aspose.words/convertutil/pixeltopoint/#pixeltopoint)(double) | تحويل وحدات البكسل إلى نقاط بدقة 96 نقطة في البوصة . |
| static [PixelToPoint](../../aspose.words/convertutil/pixeltopoint/#pixeltopoint_1)(double, double) | يحول البكسل إلى نقاط بدقة البكسل المحددة. |
| static [PointToInch](../../aspose.words/convertutil/pointtoinch/)(double) | تحويل النقاط إلى بوصة . |
| static [PointToPixel](../../aspose.words/convertutil/pointtopixel/#pointtopixel)(double) | تحويل النقاط إلى بكسل بدقة 96 نقطة في البوصة . |
| static [PointToPixel](../../aspose.words/convertutil/pointtopixel/#pointtopixel_1)(double, double) | تحويل النقاط إلى بكسل بدقة البكسل المحددة. |

### أمثلة

يوضح كيفية ضبط حجم الورق ، والاتجاه ، والهوامش ، إلى جانب الإعدادات الأخرى لقسم ما.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.PageSetup.PaperSize = PaperSize.Legal;
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
builder.PageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
builder.PageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
builder.PageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
builder.PageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
builder.PageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);

builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "PageSetup.PageMargins.docx");
```

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

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


