---
title: Class ChartDataPointCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Charts.ChartDataPointCollection 班级. 代表一个集合ChartDataPoint.
type: docs
weight: 660
url: /zh/net/aspose.words.drawing.charts/chartdatapointcollection/
---
## ChartDataPointCollection class

代表一个集合[`ChartDataPoint`](../chartdatapoint/).

```csharp
public class ChartDataPointCollection : IEnumerable<ChartDataPoint>
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words.drawing.charts/chartdatapointcollection/count/) { get; } | 返回数量[`ChartDataPoint`](../chartdatapoint/)在这个集合中。 |
| [Item](../../aspose.words.drawing.charts/chartdatapointcollection/item/) { get; } | 返回[`ChartDataPoint`](../chartdatapoint/)对于指定的索引。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [ClearFormat](../../aspose.words.drawing.charts/chartdatapointcollection/clearformat/)() | 清除所有格式[`ChartDataPoint`](../chartdatapoint/)在这个集合中。 |
| [GetEnumerator](../../aspose.words.drawing.charts/chartdatapointcollection/getenumerator/)() | 返回一个枚举器对象。 |

### 例子

显示如何使用折线图上的数据点。

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

    // 通过使它们显示为菱形来强调图表的数据点。
    foreach (ChartSeries series in chart.Series) 
        ApplyDataPoints(series, 4, MarkerSymbol.Diamond, 15);

    // 平滑表示第一个数据系列的线。
    chart.Series[0].Smooth = true;

    // 如果值为负数，则验证第一个系列的数据点不会反转它们的颜色。
    using (IEnumerator<ChartDataPoint> enumerator = chart.Series[0].DataPoints.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Assert.False(enumerator.Current.InvertIfNegative);
        }
    }

    // 为了更清晰的图表，我们可以单独清除格式。
    chart.Series[1].DataPoints[2].ClearFormat();

    // 我们也可以一次剥离整个系列的数据点。
    chart.Series[2].DataPoints.ClearFormat();

    doc.Save(ArtifactsDir + "Charts.ChartDataPoint.docx");
}

/// <summary>
/// 将多个数据点应用于系列。
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

### 也可以看看

* class [ChartDataPoint](../chartdatapoint/)
* 命名空间 [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* 部件 [Aspose.Words](../../)


