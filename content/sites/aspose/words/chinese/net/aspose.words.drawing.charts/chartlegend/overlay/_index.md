---
title: ChartLegend.Overlay
second_title: Aspose.Words for .NET API 参考
description: ChartLegend 财产. 确定是否应允许其他图表元素与图例重叠 默认值为 false
type: docs
weight: 20
url: /zh/net/aspose.words.drawing.charts/chartlegend/overlay/
---
## ChartLegend.Overlay property

确定是否应允许其他图表元素与图例重叠。 默认值为 false。

```csharp
public bool Overlay { get; set; }
```

### 例子

显示如何编辑图表图例的外观。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 450, 300);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// 将图表的图例移动到右上角。
ChartLegend legend = chart.Legend;
legend.Position = LegendPosition.TopRight;

// 通过允许它们与图例重叠，为其他图表元素（例如图形）提供更多空间。
legend.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartLegend.docx");
```

### 也可以看看

* class [ChartLegend](../)
* 命名空间 [Aspose.Words.Drawing.Charts](../../chartlegend/)
* 部件 [Aspose.Words](../../../)


