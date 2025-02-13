---
title: ChartDataPoint.Format
second_title: Aspose.Words لمراجع .NET API
description: ChartDataPoint ملكية. يوفر الوصول لتعبئة وتنسيق الخط لنقطة البيانات هذه.
type: docs
weight: 30
url: /ar/net/aspose.words.drawing.charts/chartdatapoint/format/
---
## ChartDataPoint.Format property

يوفر الوصول لتعبئة وتنسيق الخط لنقطة البيانات هذه.

```csharp
public ChartFormat Format { get; }
```

### أمثلة

يوضح كيفية تعيين التنسيق الفردي لفئات المخطط العمودي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;

// حذف السلسلة الافتراضية التي تم إنشاؤها.
chart.Series.Clear();

// إضافة سلسلة جديدة.
ChartSeries series = chart.Series.Add("Series 1",
    new[] { "Category 1", "Category 2", "Category 3", "Category 4" },
    new double[] { 1, 2, 3, 4 });

// تعيين تنسيق العمود.
ChartDataPointCollection dataPoints = series.DataPoints;
dataPoints[0].Format.Fill.PresetTextured(PresetTexture.Denim);
dataPoints[1].Format.Fill.ForeColor = Color.Red;
dataPoints[2].Format.Fill.ForeColor = Color.Yellow;
dataPoints[3].Format.Fill.ForeColor = Color.Blue;

doc.Save(ArtifactsDir + "Charts.DataPointsFormatting.docx");
```

### أنظر أيضا

* class [ChartFormat](../../chartformat/)
* class [ChartDataPoint](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartdatapoint/)
* المجسم [Aspose.Words](../../../)


