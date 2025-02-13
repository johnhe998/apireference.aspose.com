---
title: Class AxisScaling
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Charts.AxisScaling فصل. يمثل خيارات القياس للمحور.
type: docs
weight: 560
url: /ar/net/aspose.words.drawing.charts/axisscaling/
---
## AxisScaling class

يمثل خيارات القياس للمحور.

```csharp
public class AxisScaling
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [AxisScaling](axisscaling/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [LogBase](../../aspose.words.drawing.charts/axisscaling/logbase/) { get; set; } | الحصول على أو تعيين القاعدة اللوغاريتمية للمحور اللوغاريتمي. |
| [Maximum](../../aspose.words.drawing.charts/axisscaling/maximum/) { get; set; } | الحصول على أو تحديد الحد الأقصى لقيمة المحور. |
| [Minimum](../../aspose.words.drawing.charts/axisscaling/minimum/) { get; set; } | الحصول على أو تعيين الحد الأدنى لقيمة المحور. |
| [Type](../../aspose.words.drawing.charts/axisscaling/type/) { get; set; } | الحصول على نوع القياس للمحور أو تعيينه. |

### أمثلة

يوضح كيفية تطبيق القياس اللوغاريتمي على محور مخطط.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape chartShape = builder.InsertChart(ChartType.Scatter, 450, 300);
Chart chart = chartShape.Chart;

// امسح سلسلة بيانات العرض التوضيحي للرسم البياني لتبدأ بمخطط نظيف.
chart.Series.Clear();

// أدخل سلسلة بإحداثيات X / Y لخمس نقاط.
chart.Series.Add("Series 1", 
    new[] { 1.0, 2.0, 3.0, 4.0, 5.0 }, 
    new[] { 1.0, 20.0, 400.0, 8000.0, 160000.0 });

// مقياس المحور X خطي بشكل افتراضي ،
// عرض القيم المتزايدة بالتساوي التي تغطي نطاق قيمة X لدينا (0 ، 1 ، 2 ، 3 ...).
// لا يعد المحور الخطي مثاليًا لقيمنا Y
// نظرًا لأن النقاط التي تحتوي على قيم Y الأصغر سيكون من الصعب قراءتها.
// مقياس لوغاريتمي بقاعدة 20 (1 ، 20 ، 400 ، 8000 ...)
// سينشر النقاط المرسومة ، مما يسمح لنا بقراءة قيمها على الرسم البياني بسهولة أكبر.
chart.AxisY.Scaling.Type = AxisScaleType.Logarithmic;
chart.AxisY.Scaling.LogBase = 20;

doc.Save(ArtifactsDir + "Charts.AxisScaling.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* المجسم [Aspose.Words](../../)


