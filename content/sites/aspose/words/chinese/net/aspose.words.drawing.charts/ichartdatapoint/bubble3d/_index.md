---
title: IChartDataPoint.Bubble3D
second_title: Aspose.Words for .NET API 参考
description: IChartDataPoint 财产. 指定气泡图中的气泡是否应应用 3D 效果
type: docs
weight: 10
url: /zh/net/aspose.words.drawing.charts/ichartdatapoint/bubble3d/
---
## IChartDataPoint.Bubble3D property

指定气泡图中的气泡是否应应用 3-D 效果。

```csharp
public bool Bubble3D { get; set; }
```

### 例子

展示如何将 3D 效果与气泡图结合使用。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Bubble3D, 500, 350);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);
Assert.True(chart.Series[0].Bubble3D);

// 将数据标签应用于显示其直径的每个气泡。
for (int i = 0; i < 3; i++)
{
    chart.Series[0].HasDataLabels = true;
    chart.Series[0].DataLabels[i].ShowBubbleSize = true;
}

doc.Save(ArtifactsDir + "Charts.Bubble3D.docx");
```

### 也可以看看

* interface [IChartDataPoint](../)
* 命名空间 [Aspose.Words.Drawing.Charts](../../ichartdatapoint/)
* 部件 [Aspose.Words](../../../)


