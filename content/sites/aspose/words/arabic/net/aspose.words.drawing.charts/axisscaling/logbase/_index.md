---
title: AxisScaling.LogBase
second_title: Aspose.Words لمراجع .NET API
description: AxisScaling ملكية. الحصول على أو تعيين القاعدة اللوغاريتمية للمحور اللوغاريتمي.
type: docs
weight: 20
url: /ar/net/aspose.words.drawing.charts/axisscaling/logbase/
---
## AxisScaling.LogBase property

الحصول على أو تعيين القاعدة اللوغاريتمية للمحور اللوغاريتمي.

```csharp
public double LogBase { get; set; }
```

### ملاحظات

الخاصية غير مدعومة بواسطة مخططات MS Office 2016 الجديدة.

النطاق الصالح لقيمة النقطة العائمة أكبر من أو يساوي 2 وأقل من أو يساوي 1000. يكون للخاصية تأثير فقط إذا[`Type`](../type/) مضبوطة على Logarithmic.

تعيين هذه الخاصية يعيّن[`Type`](../type/) الملكية لLogarithmic .

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

* class [AxisScaling](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../axisscaling/)
* المجسم [Aspose.Words](../../../)


