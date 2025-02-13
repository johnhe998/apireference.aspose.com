---
title: AxisScaling.Type
second_title: Aspose.Words لمراجع .NET API
description: AxisScaling ملكية. الحصول على نوع القياس للمحور أو تعيينه.
type: docs
weight: 50
url: /ar/net/aspose.words.drawing.charts/axisscaling/type/
---
## AxisScaling.Type property

الحصول على نوع القياس للمحور أو تعيينه.

```csharp
public AxisScaleType Type { get; set; }
```

### ملاحظات

ملفLinear القيمة هي الوحيدة المسموح بها في مخططات MS Office 2016 الجديدة.

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

* enum [AxisScaleType](../../axisscaletype/)
* class [AxisScaling](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../axisscaling/)
* المجسم [Aspose.Words](../../../)


