---
title: ChartDataLabelCollection.ShowLegendKey
second_title: Aspose.Words لمراجع .NET API
description: ChartDataLabelCollection ملكية. يسمح بتحديد ما إذا كان سيتم عرض مفتاح وسيلة الإيضاح لتسميات البيانات الخاصة بالسلسلة بأكملها. القيمة الافتراضية هي خاطئة .
type: docs
weight: 90
url: /ar/net/aspose.words.drawing.charts/chartdatalabelcollection/showlegendkey/
---
## ChartDataLabelCollection.ShowLegendKey property

يسمح بتحديد ما إذا كان سيتم عرض مفتاح وسيلة الإيضاح لتسميات البيانات الخاصة بالسلسلة بأكملها. القيمة الافتراضية هي **خاطئة** .

```csharp
public bool ShowLegendKey { get; set; }
```

### ملاحظات

يمكن تجاوز القيمة المحددة لهذه الخاصية لتسمية بيانات فردية باستخدام the [`ShowLegendKey`](../../chartdatalabel/showlegendkey/) الملكية .

### أمثلة

يوضح كيفية العمل باستخدام تسميات البيانات الخاصة بالمخطط الدائري.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Pie, 500, 300).Chart;

// امسح سلسلة بيانات العرض التوضيحي للرسم البياني لتبدأ بمخطط نظيف.
chart.Series.Clear();

// أدخل سلسلة مخططات مخصصة مع اسم فئة لكل قطاع ، وجدول تكرارها.
ChartSeries series = chart.Series.Add("Aspose Test Series",
    new[] { "Word", "PDF", "Excel" },
    new[] { 2.7, 3.2, 0.8 });

// تمكين تسميات البيانات التي ستعرض كلاً من النسبة المئوية والتكرار لكل قطاع ، وتعديل مظهرها.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowLeaderLines = true;
dataLabels.ShowLegendKey = true;
dataLabels.ShowPercentage = true;
dataLabels.ShowValue = true;
dataLabels.Separator = "; ";

doc.Save(ArtifactsDir + "Charts.DataLabelsPieChart.docx");
```

### أنظر أيضا

* class [ChartDataLabelCollection](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* المجسم [Aspose.Words](../../../)


