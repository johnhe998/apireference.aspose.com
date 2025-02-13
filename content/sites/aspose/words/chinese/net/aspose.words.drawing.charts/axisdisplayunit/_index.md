---
title: Class AxisDisplayUnit
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Charts.AxisDisplayUnit 班级. 提供对数值轴显示单位缩放选项的访问
type: docs
weight: 540
url: /zh/net/aspose.words.drawing.charts/axisdisplayunit/
---
## AxisDisplayUnit class

提供对数值轴显示单位缩放选项的访问。

```csharp
public class AxisDisplayUnit
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [AxisDisplayUnit](axisdisplayunit/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [CustomUnit](../../aspose.words.drawing.charts/axisdisplayunit/customunit/) { get; set; } | 获取或设置一个用户定义的除数来缩放值轴上的显示单位。 |
| [Document](../../aspose.words.drawing.charts/axisdisplayunit/document/) { get; } | 返回标题持有者所属的文档。 |
| [Unit](../../aspose.words.drawing.charts/axisdisplayunit/unit/) { get; set; } | 获取或设置显示单元的缩放值作为预定义值之一。 |

### 例子

显示如何操作刻度线和图表轴的显示值。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);

// 将 Y 轴的小刻度线设置为远离绘图区域，
// 和跨轴的主要刻度线。
ChartAxis axis = chart.AxisY;
axis.MajorTickMark = AxisTickMark.Cross;
axis.MinorTickMark = AxisTickMark.Outside;

// 将它们的 Y 轴设置为每 10 个单位显示一个主要刻度，每 1 个单位显示一个次要刻度。
axis.MajorUnit = 10;
axis.MinorUnit = 1;

// 将 Y 轴范围设置为 -10 和 20。
// 这个 Y 轴现在将显示 4 个主要刻度线和 27 个次要刻度线。
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(20);

// 对于 X 轴，每 10 个单位设置一次主刻度线，
// 2.5 个单位的每个次要刻度线。
axis = chart.AxisX;
axis.MajorUnit = 10;
axis.MinorUnit = 2.5;

// 将两种类型的刻度线配置为出现在图形绘图区域内。
axis.MajorTickMark = AxisTickMark.Inside;
axis.MinorTickMark = AxisTickMark.Inside;

// 设置 X 轴边界，使 X 轴跨越 5 个主要刻度线和 12 个次要刻度线。
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(30);
axis.TickLabelAlignment = ParagraphAlignment.Right;

Assert.AreEqual(1, axis.TickLabelSpacing);

// 将刻度标签设置为以百万为单位显示它们的值。
axis.DisplayUnit.Unit = AxisBuiltInUnit.Millions;

// 我们可以设置一个更具体的值，刻度标签将通过该值显示它们的值。
// 这个语句和上面那个是等价的。
axis.DisplayUnit.CustomUnit = 1000000;
doc.Save(ArtifactsDir + "Charts.AxisDisplayUnit.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* 部件 [Aspose.Words](../../)


