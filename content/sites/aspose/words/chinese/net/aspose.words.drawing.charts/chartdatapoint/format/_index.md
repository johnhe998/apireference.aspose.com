---
title: ChartDataPoint.Format
second_title: Aspose.Words for .NET API 参考
description: ChartDataPoint 财产. 提供对此数据点的填充和线条格式的访问
type: docs
weight: 30
url: /zh/net/aspose.words.drawing.charts/chartdatapoint/format/
---
## ChartDataPoint.Format property

提供对此数据点的填充和线条格式的访问。

```csharp
public ChartFormat Format { get; }
```

### 例子

显示如何为柱形图的类别设置单独的格式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;

// 删除默认生成的系列。
chart.Series.Clear();

// 添加新系列。
ChartSeries series = chart.Series.Add("Series 1",
    new[] { "Category 1", "Category 2", "Category 3", "Category 4" },
    new double[] { 1, 2, 3, 4 });

// 设置列格式。
ChartDataPointCollection dataPoints = series.DataPoints;
dataPoints[0].Format.Fill.PresetTextured(PresetTexture.Denim);
dataPoints[1].Format.Fill.ForeColor = Color.Red;
dataPoints[2].Format.Fill.ForeColor = Color.Yellow;
dataPoints[3].Format.Fill.ForeColor = Color.Blue;

doc.Save(ArtifactsDir + "Charts.DataPointsFormatting.docx");
```

### 也可以看看

* class [ChartFormat](../../chartformat/)
* class [ChartDataPoint](../)
* 命名空间 [Aspose.Words.Drawing.Charts](../../chartdatapoint/)
* 部件 [Aspose.Words](../../../)


