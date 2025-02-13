---
title: AxisBound.Value
second_title: Aspose.Words لمراجع .NET API
description: AxisBound ملكية. إرجاع القيمة الرقمية لحد المحور .
type: docs
weight: 30
url: /ar/net/aspose.words.drawing.charts/axisbound/value/
---
## AxisBound.Value property

إرجاع القيمة الرقمية لحد المحور .

```csharp
public double Value { get; }
```

### أمثلة

يوضح كيفية تعيين حدود المحور المخصصة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape chartShape = builder.InsertChart(ChartType.Scatter, 450, 300);
Chart chart = chartShape.Chart;

// امسح سلسلة بيانات العرض التوضيحي للرسم البياني لتبدأ بمخطط نظيف.
chart.Series.Clear();

// أضف سلسلة ذات مصفوفتين عشريتين. تحتوي المصفوفة الأولى على قيم X ،
// والثاني يحتوي على قيم Y المقابلة للنقاط في المخطط المبعثر.
chart.Series.Add("Series 1", 
    new[] { 1.1, 5.4, 7.9, 3.5, 2.1, 9.7 }, 
    new[] { 2.1, 0.3, 0.6, 3.3, 1.4, 1.9 });

// بشكل افتراضي ، يتم تطبيق القياس الافتراضي على محوري الرسم البياني X و Y ،
// بحيث يكون كلا نطاقيهما كبيرًا بما يكفي ليشمل كل قيمة X و Y لكل سلسلة.
Assert.True(chart.AxisX.Scaling.Minimum.IsAuto);

// يمكننا تحديد حدود المحور الخاصة بنا.
// في هذه الحالة ، سنجعل مساطر المحور X و Y تظهر نطاقًا من 0 إلى 10.
chart.AxisX.Scaling.Minimum = new AxisBound(0);
chart.AxisX.Scaling.Maximum = new AxisBound(10);
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(10);

Assert.False(chart.AxisX.Scaling.Minimum.IsAuto);
Assert.False(chart.AxisY.Scaling.Minimum.IsAuto);

// إنشاء مخطط خطي بسلسلة تتطلب نطاقًا من التواريخ على المحور السيني والقيم العشرية للمحور ص.
chartShape = builder.InsertChart(ChartType.Line, 450, 300);
chart = chartShape.Chart;
chart.Series.Clear();

DateTime[] dates = { new DateTime(1973, 5, 11),
    new DateTime(1981, 2, 4),
    new DateTime(1985, 9, 23),
    new DateTime(1989, 6, 28),
    new DateTime(1994, 12, 15)
};

chart.Series.Add("Series 1", dates, new[] { 3.0, 4.7, 5.9, 7.1, 8.9 });

// يمكننا أيضًا تعيين حدود المحور في شكل تواريخ أيضًا ، مع قصر الرسم البياني على فترة زمنية.
// سيؤدي تعيين النطاق إلى 1980-1990 إلى حذف قيمتي السلاسل
// التي تقع خارج النطاق من الرسم البياني.
chart.AxisX.Scaling.Minimum = new AxisBound(new DateTime(1980, 1, 1));
chart.AxisX.Scaling.Maximum = new AxisBound(new DateTime(1990, 1, 1));

doc.Save(ArtifactsDir + "Charts.AxisBound.docx");
```

### أنظر أيضا

* class [AxisBound](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../axisbound/)
* المجسم [Aspose.Words](../../../)


