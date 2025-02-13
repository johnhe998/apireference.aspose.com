---
title: ChartAxis.Hidden
second_title: Aspose.Words لمراجع .NET API
description: ChartAxis ملكية. الحصول على أو تعيين علامة تشير إلى ما إذا كان هذا المحور مخفيًا أم لا.
type: docs
weight: 80
url: /ar/net/aspose.words.drawing.charts/chartaxis/hidden/
---
## ChartAxis.Hidden property

الحصول على أو تعيين علامة تشير إلى ما إذا كان هذا المحور مخفيًا أم لا.

```csharp
public bool Hidden { get; set; }
```

### ملاحظات

القيمة الافتراضية هي **خاطئة** .

### أمثلة

يوضح كيفية إخفاء محاور الرسم البياني.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// امسح سلسلة بيانات العرض التوضيحي للرسم البياني لتبدأ بمخطط نظيف.
chart.Series.Clear();

// أضف سلسلة مخصصة مع فئات للمحور X والقيم العشرية ذات الصلة للمحور Y.
chart.Series.Add("AW Series 1",
    new[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2 });

 // إخفاء محاور المخطط لتبسيط مظهر المخطط.
chart.AxisX.Hidden = true;
chart.AxisY.Hidden = true;

doc.Save(ArtifactsDir + "Charts.HideChartAxis.docx");
```

### أنظر أيضا

* class [ChartAxis](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartaxis/)
* المجسم [Aspose.Words](../../../)


