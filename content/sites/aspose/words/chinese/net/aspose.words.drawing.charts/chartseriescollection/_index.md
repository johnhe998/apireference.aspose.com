---
title: Class ChartSeriesCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Charts.ChartSeriesCollection 班级. 代表一个集合ChartSeries.
type: docs
weight: 740
url: /zh/net/aspose.words.drawing.charts/chartseriescollection/
---
## ChartSeriesCollection class

代表一个集合[`ChartSeries`](../chartseries/).

```csharp
public class ChartSeriesCollection : IEnumerable<ChartSeries>
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words.drawing.charts/chartseriescollection/count/) { get; } | 返回数量[`ChartSeries`](../chartseries/)在这个集合中。 |
| [Item](../../aspose.words.drawing.charts/chartseriescollection/item/) { get; } | 返回一个[`ChartSeries`](../chartseries/)在指定的索引处。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_2)(string, DateTime[], double[]) | 添加新的[`ChartSeries`](../chartseries/)到此集合。 使用此方法将系列添加到任何类型的区域、雷达和股票图表。 |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add)(string, double[], double[]) | 添加新的[`ChartSeries`](../chartseries/)到此集合。 使用此方法将系列添加到任何类型的散点图。 |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_3)(string, string[], double[]) | 添加新的[`ChartSeries`](../chartseries/)到此集合。 使用此方法将系列添加到任何类型的条形图、柱形图、折线图和曲面图。 |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_1)(string, double[], double[], double[]) | 添加新的[`ChartSeries`](../chartseries/)到此集合。 使用此方法将系列添加到任何类型的气泡图。 |
| [Clear](../../aspose.words.drawing.charts/chartseriescollection/clear/)() | 删除所有[`ChartSeries`](../chartseries/)来自这个集合。 |
| [GetEnumerator](../../aspose.words.drawing.charts/chartseriescollection/getenumerator/)() | 返回一个枚举器对象。 |
| [RemoveAt](../../aspose.words.drawing.charts/chartseriescollection/removeat/)(int) | 删除一个[`ChartSeries`](../chartseries/)在指定的索引处。 |

### 例子

显示如何在图表中添加和删除系列数据。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入一个柱形图，默认包含三个系列的演示数据。
Shape chartShape = builder.InsertChart(ChartType.Column, 400, 300);
Chart chart = chartShape.Chart;

// 每个系列有四个十进制值：四个类别中的每一个。
// 三列的四个集群将代表此数据。
ChartSeriesCollection chartData = chart.Series;

Assert.AreEqual(3, chartData.Count);

// 打印图表中每个系列的名称。
using (IEnumerator<ChartSeries> enumerator = chart.Series.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Console.WriteLine(enumerator.Current.Name);
    }
}

// 这些是图表中类别的名称。
string[] categories = { "Category 1", "Category 2", "Category 3", "Category 4" };

// 我们可以为现有类别添加具有新值的系列。
// 这个图表现在将包含四个四列的集群。
chart.Series.Add("Series 4", categories, new[] { 4.4, 7.0, 3.5, 2.1 });

// 图表系列也可以通过索引移除，就像这样。
// 这将删除图表随附的三个演示系列之一。
chartData.RemoveAt(2);

Assert.False(chartData.Any(s => s.Name == "Series 3"));

// 我们也可以用这个方法一次性清除所有图表的数据。
// 创建新图表时，这是擦除所有演示数据的方法
// 在我们开始处理空白图表之前。
chartData.Clear();
```

### 也可以看看

* class [ChartSeries](../chartseries/)
* 命名空间 [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* 部件 [Aspose.Words](../../)


