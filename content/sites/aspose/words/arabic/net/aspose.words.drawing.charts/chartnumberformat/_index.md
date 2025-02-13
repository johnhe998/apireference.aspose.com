---
title: Class ChartNumberFormat
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Charts.ChartNumberFormat فصل. يمثل تنسيق الأرقام للعنصر الأصل.
type: docs
weight: 720
url: /ar/net/aspose.words.drawing.charts/chartnumberformat/
---
## ChartNumberFormat class

يمثل تنسيق الأرقام للعنصر الأصل.

```csharp
public class ChartNumberFormat
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [FormatCode](../../aspose.words.drawing.charts/chartnumberformat/formatcode/) { get; set; } | الحصول على أو تعيين رمز التنسيق المطبق على تسمية البيانات. |
| [IsLinkedToSource](../../aspose.words.drawing.charts/chartnumberformat/islinkedtosource/) { get; set; } | يحدد ما إذا كان كود التنسيق مرتبطًا بخلية مصدر. القيمة الافتراضية هي true . |

### أمثلة

يوضح كيفية تعيين التنسيق لقيم المخطط.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// امسح سلسلة بيانات العرض التوضيحي للرسم البياني لتبدأ بمخطط نظيف.
chart.Series.Clear();

// أضف سلسلة مخصصة إلى الرسم البياني بفئات للمحور السيني ،
 // والقيم الرقمية الكبيرة الخاصة بالمحور ص.
chart.Series.Add("Aspose Test Series",
    new [] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });

 // قم بتعيين تنسيق الأرقام الخاص بعلامات تحديد المحور Y على عدم تجميع الأرقام بفاصلات.
chart.AxisY.NumberFormat.FormatCode = "#,##0";

// يمكن لهذه العلامة تجاوز القيمة أعلاه ورسم تنسيق الأرقام من الخلية المصدر.
Assert.False(chart.AxisY.NumberFormat.IsLinkedToSource);

doc.Save(ArtifactsDir + "Charts.SetNumberFormatToChartAxis.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* المجسم [Aspose.Words](../../)


