---
title: ChartDataLabelCollection.ShowLeaderLines
second_title: Aspose.Words for .NET API 参考
description: ChartDataLabelCollection 财产. 允许指定是否需要为整个系列的数据标签显示数据标签引出线 默认值为 错误的.
type: docs
weight: 80
url: /zh/net/aspose.words.drawing.charts/chartdatalabelcollection/showleaderlines/
---
## ChartDataLabelCollection.ShowLeaderLines property

允许指定是否需要为整个系列的数据标签显示数据标签引出线。 默认值为 **错误的**.

```csharp
public bool ShowLeaderLines { get; set; }
```

### 评论

仅适用于饼图。 引导线在数据标签与其对应的数据点之间创建视觉连接。

可以使用 the 为单个数据标签覆盖为此属性定义的值[`ShowLeaderLines`](../../chartdatalabel/showleaderlines/)财产。

### 例子

展示如何使用饼图的数据标签。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Pie, 500, 300).Chart;

// 清除图表的演示数据系列以从干净的图表开始。
chart.Series.Clear();

// 插入一个自定义图表系列，其中包含每个部门的类别名称及其频率表。
ChartSeries series = chart.Series.Add("Aspose Test Series",
    new[] { "Word", "PDF", "Excel" },
    new[] { 2.7, 3.2, 0.8 });

// 启用将显示每个扇区的百分比和频率的数据标签，并修改它们的外观。
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowLeaderLines = true;
dataLabels.ShowLegendKey = true;
dataLabels.ShowPercentage = true;
dataLabels.ShowValue = true;
dataLabels.Separator = "; ";

doc.Save(ArtifactsDir + "Charts.DataLabelsPieChart.docx");
```

### 也可以看看

* class [ChartDataLabelCollection](../)
* 命名空间 [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* 部件 [Aspose.Words](../../../)


