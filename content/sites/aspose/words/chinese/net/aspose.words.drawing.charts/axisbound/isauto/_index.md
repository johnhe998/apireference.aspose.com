---
title: AxisBound.IsAuto
second_title: Aspose.Words for .NET API 参考
description: AxisBound 财产. 返回一个标志指示应自动确定轴边界
type: docs
weight: 20
url: /zh/net/aspose.words.drawing.charts/axisbound/isauto/
---
## AxisBound.IsAuto property

返回一个标志，指示应自动确定轴边界。

```csharp
public bool IsAuto { get; }
```

### 例子

显示如何设置自定义轴边界。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape chartShape = builder.InsertChart(ChartType.Scatter, 450, 300);
Chart chart = chartShape.Chart;

// 清除图表的演示数据系列以从干净的图表开始。
chart.Series.Clear();

// 添加一个包含两个十进制数组的系列。第一个数组包含 X 值，
// 第二个包含散点图中点的相应 Y 值。
chart.Series.Add("Series 1", 
    new[] { 1.1, 5.4, 7.9, 3.5, 2.1, 9.7 }, 
    new[] { 2.1, 0.3, 0.6, 3.3, 1.4, 1.9 });

// 默认情况下，默认缩放应用于图形的 X 和 Y 轴，
// 这样它们的范围都足够大，可以包含每个系列的每个 X 和 Y 值。
Assert.True(chart.AxisX.Scaling.Minimum.IsAuto);

// 我们可以定义自己的轴边界。
// 在这种情况下，我们将使 X 轴和 Y 轴标尺都显示 0 到 10 的范围。
chart.AxisX.Scaling.Minimum = new AxisBound(0);
chart.AxisX.Scaling.Maximum = new AxisBound(10);
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(10);

Assert.False(chart.AxisX.Scaling.Minimum.IsAuto);
Assert.False(chart.AxisY.Scaling.Minimum.IsAuto);

// 创建一个折线图，其系列需要 X 轴上的日期范围和 Y 轴上的十进制值。
chartShape = builder.InsertChart(ChartType.Line, 450, 300);
chart = chartShape.Chart;
chart.Series.Clear();

DateTime[] dates = { new DateTime(1973, 5, 11),
    new DateTime(1981, 2, 4),
    new DateTime(1985, 9, 23),
    new DateTime(1989, 6, 28),
    new DateTime(1994, 12, 15)
};

chart.Series.Add("Series 1", dates, new[] { 3.0, 4.7, 5.9, 7.1, 8.9 });

// 我们也可以以日期的形式设置轴边界，将图表限制在一个周期内。
// 将范围设置为 1980-1990 将省略两个系列值
// 超出图表范围。
chart.AxisX.Scaling.Minimum = new AxisBound(new DateTime(1980, 1, 1));
chart.AxisX.Scaling.Maximum = new AxisBound(new DateTime(1990, 1, 1));

doc.Save(ArtifactsDir + "Charts.AxisBound.docx");
```

### 也可以看看

* class [AxisBound](../)
* 命名空间 [Aspose.Words.Drawing.Charts](../../axisbound/)
* 部件 [Aspose.Words](../../../)


