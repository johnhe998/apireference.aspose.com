---
title: Enum MarkerSymbol
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Charts.MarkerSymbol تعداد. يحدد نمط رمز العلامة .
type: docs
weight: 790
url: /ar/net/aspose.words.drawing.charts/markersymbol/
---
## MarkerSymbol enumeration

يحدد نمط رمز العلامة .

```csharp
public enum MarkerSymbol
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Default | `0` | تحديد رمز علامة افتراضي يتم رسمه عند كل نقطة بيانات. |
| Circle | `1` | يحدد دائرة يتم رسمها عند كل نقطة بيانات. |
| Dash | `2` | تحديد يجب رسم شرطة عند كل نقطة بيانات. |
| Diamond | `3` | يحدد ماسة يجب رسمها عند كل نقطة بيانات. |
| Dot | `4` | يحدد نقطة يتم رسمها عند كل نقطة بيانات. |
| None | `5` | يحدد أي شيء يجب رسمه في كل نقطة بيانات. |
| Picture | `6` | يحدد صورة يجب رسمها عند كل نقطة بيانات. |
| Plus | `7` | يحدد علامة زائد يتم رسمها عند كل نقطة بيانات. |
| Square | `8` | يحدد مربعًا يجب رسمه عند كل نقطة بيانات. |
| Star | `9` | يحدد أنه يجب رسم نجمة عند كل نقطة بيانات. |
| Triangle | `10` | يحدد مثلث يجب رسمه عند كل نقطة بيانات. |
| X | `11` | يحدد X يجب رسمه عند كل نقطة بيانات. |

### أمثلة

يوضح كيفية التعامل مع نقاط البيانات على مخطط خطي.

```csharp
[Test]
public void ChartDataPoint()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    Shape shape = builder.InsertChart(ChartType.Line, 500, 350);
    Chart chart = shape.Chart;

    Assert.AreEqual(3, chart.Series.Count);
    Assert.AreEqual("Series 1", chart.Series[0].Name);
    Assert.AreEqual("Series 2", chart.Series[1].Name);
    Assert.AreEqual("Series 3", chart.Series[2].Name);

    // قم بتأكيد نقاط بيانات المخطط بجعلها تظهر كأشكال ماسية.
    foreach (ChartSeries series in chart.Series) 
        ApplyDataPoints(series, 4, MarkerSymbol.Diamond, 15);

    // قم بتمهيد الخط الذي يمثل سلسلة البيانات الأولى.
    chart.Series[0].Smooth = true;

    // تحقق من أن نقاط البيانات للسلسلة الأولى لن تعكس ألوانها إذا كانت القيمة سالبة.
    using (IEnumerator<ChartDataPoint> enumerator = chart.Series[0].DataPoints.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Assert.False(enumerator.Current.InvertIfNegative);
        }
    }

    // للحصول على رسم بياني أكثر وضوحًا ، يمكننا مسح التنسيق بشكل فردي.
    chart.Series[1].DataPoints[2].ClearFormat();

    // يمكننا أيضًا تجريد سلسلة كاملة من نقاط البيانات مرة واحدة.
    chart.Series[2].DataPoints.ClearFormat();

    doc.Save(ArtifactsDir + "Charts.ChartDataPoint.docx");
}

/// <summary>
/// يطبق عددًا من نقاط البيانات على سلسلة.
/// </summary>
private static void ApplyDataPoints(ChartSeries series, int dataPointsCount, MarkerSymbol markerSymbol, int dataPointSize)
{
    for (int i = 0; i < dataPointsCount; i++)
    {
        ChartDataPoint point = series.DataPoints[i];
        point.Marker.Symbol = markerSymbol;
        point.Marker.Size = dataPointSize;

        Assert.AreEqual(i, point.Index);
    }
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* المجسم [Aspose.Words](../../)


