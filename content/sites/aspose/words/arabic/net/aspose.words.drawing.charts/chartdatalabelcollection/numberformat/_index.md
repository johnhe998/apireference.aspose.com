---
title: ChartDataLabelCollection.NumberFormat
second_title: Aspose.Words لمراجع .NET API
description: ChartDataLabelCollection ملكية. يحصل على ملفChartNumberFormat مثال يسمح بتعيين تنسيق رقم لتسميات البيانات لسلسلة بأكملها.
type: docs
weight: 30
url: /ar/net/aspose.words.drawing.charts/chartdatalabelcollection/numberformat/
---
## ChartDataLabelCollection.NumberFormat property

يحصل على ملف[`ChartNumberFormat`](../../chartnumberformat/) مثال يسمح بتعيين تنسيق رقم لتسميات البيانات لسلسلة بأكملها.

```csharp
public ChartNumberFormat NumberFormat { get; }
```

### أمثلة

يوضح كيفية تمكين وتكوين تسميات البيانات لسلسلة مخطط.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أضف مخططًا خطيًا ، ثم امسح سلسلة البيانات التجريبية لتبدأ بمخطط نظيف ،
// ثم قم بتعيين عنوان.
Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;
chart.Series.Clear();
chart.Title.Text = "Monthly sales report";

// أدخل سلسلة مخطط مخصصة مع الأشهر كفئات للمحور السيني ،
// والمبالغ العشرية ذات الصلة للمحور ص.
ChartSeries series = chart.Series.Add("Revenue", 
    new[] { "January", "February", "March" }, 
    new[] { 25.611d, 21.439d, 33.750d });

// تمكين تسميات البيانات ، ثم تطبيق تنسيق أرقام مخصص للقيم المعروضة في تسميات البيانات.
// سيعامل هذا التنسيق القيم العشرية المعروضة كملايين الدولارات الأمريكية.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowValue = true;
dataLabels.NumberFormat.FormatCode = "\"US$\" #,##0.000\"M\"";

doc.Save(ArtifactsDir + "Charts.DataLabelNumberFormat.docx");
```

### أنظر أيضا

* class [ChartNumberFormat](../../chartnumberformat/)
* class [ChartDataLabelCollection](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* المجسم [Aspose.Words](../../../)


