---
title: ChartDataLabelCollection.ShowBubbleSize
second_title: Aspose.Words لمراجع .NET API
description: ChartDataLabelCollection ملكية. يسمح بتحديد ما إذا كان سيتم عرض حجم الفقاعة لتسميات البيانات الخاصة بالسلسلة بأكملها. ينطبق فقط على المخططات الفقاعية. القيمة الافتراضية هي خاطئة .
type: docs
weight: 50
url: /ar/net/aspose.words.drawing.charts/chartdatalabelcollection/showbubblesize/
---
## ChartDataLabelCollection.ShowBubbleSize property

يسمح بتحديد ما إذا كان سيتم عرض حجم الفقاعة لتسميات البيانات الخاصة بالسلسلة بأكملها. ينطبق فقط على المخططات الفقاعية. القيمة الافتراضية هي **خاطئة** .

```csharp
public bool ShowBubbleSize { get; set; }
```

### ملاحظات

يمكن تجاوز القيمة المحددة لهذه الخاصية لتسمية بيانات فردية باستخدام the [`ShowBubbleSize`](../../chartdatalabel/showbubblesize/) الملكية .

### أمثلة

يوضح كيفية العمل باستخدام تسميات البيانات لمخطط فقاعي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Bubble, 500, 300).Chart;

// امسح سلسلة بيانات العرض التوضيحي للرسم البياني لتبدأ بمخطط نظيف.
chart.Series.Clear();

 // أضف سلسلة مخصصة بإحداثيات X / Y وقطر كل من الفقاعات.
ChartSeries series = chart.Series.Add("Aspose Test Series",
    new[] { 2.9, 3.5, 1.1, 4.0, 4.0 },
    new[] { 1.9, 8.5, 2.1, 6.0, 1.5 },
    new[] { 9.0, 4.5, 2.5, 8.0, 5.0 });

// تمكين تسميات البيانات ، ثم تعديل مظهرها.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowBubbleSize = true;
dataLabels.ShowCategoryName = true;
dataLabels.ShowSeriesName = true;
dataLabels.Separator = " & ";

doc.Save(ArtifactsDir + "Charts.DataLabelsBubbleChart.docx");
```

### أنظر أيضا

* class [ChartDataLabelCollection](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* المجسم [Aspose.Words](../../../)


