---
title: ChartNumberFormat.FormatCode
second_title: Aspose.Words لمراجع .NET API
description: ChartNumberFormat ملكية. الحصول على أو تعيين رمز التنسيق المطبق على تسمية البيانات.
type: docs
weight: 10
url: /ar/net/aspose.words.drawing.charts/chartnumberformat/formatcode/
---
## ChartNumberFormat.FormatCode property

الحصول على أو تعيين رمز التنسيق المطبق على تسمية البيانات.

```csharp
public string FormatCode { get; set; }
```

### ملاحظات

يتم استخدام تنسيق الأرقام لتغيير الطريقة التي تظهر بها القيمة في تسمية البيانات ويمكن استخدامها في بعض الطرق الإبداعية للغاية. أمثلة تنسيقات الأرقام:

الرقم - "#، ## 0.00"

العملة - "\" $ \ "#، ## 0.00"

الوقت - "[$ -x-systime] h: mm: ss AM / PM"

التاريخ - "يوم / شهر / سنة"

النسبة المئوية - "0.00٪"

جزء - "# ؟/؟"

علمي - "0.00E + 00"

نص - "@"

محاسبة - "_- \" $ \ "* #، ## 0.00 _-؛ - \" $ \ "* #، ## 0.00 _-؛ _- \" $ \ "* \" - \ "؟؟ _ -؛ - @ - "

مخصص باللون - "[أحمر] - # ، ## 0.0"

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

* class [ChartNumberFormat](../)
* مساحة الاسم [Aspose.Words.Drawing.Charts](../../chartnumberformat/)
* المجسم [Aspose.Words](../../../)


