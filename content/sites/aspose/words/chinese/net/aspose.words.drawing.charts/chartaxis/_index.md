---
title: Class ChartAxis
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Charts.ChartAxis 班级. 表示图表的轴选项
type: docs
weight: 610
url: /zh/net/aspose.words.drawing.charts/chartaxis/
---
## ChartAxis class

表示图表的轴选项。

```csharp
public class ChartAxis
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [AxisBetweenCategories](../../aspose.words.drawing.charts/chartaxis/axisbetweencategories/) { get; set; } | 获取或设置一个标志，指示值轴是否与类别之间的类别轴相交。 |
| [BaseTimeUnit](../../aspose.words.drawing.charts/chartaxis/basetimeunit/) { get; set; } | 返回或设置时间类别轴上表示的最小时间单位。 |
| [CategoryType](../../aspose.words.drawing.charts/chartaxis/categorytype/) { get; set; } | 获取或设置类别轴的类型。 |
| [Crosses](../../aspose.words.drawing.charts/chartaxis/crosses/) { get; set; } | 指定此轴如何与垂直轴相交。 |
| [CrossesAt](../../aspose.words.drawing.charts/chartaxis/crossesat/) { get; set; } | 指定轴在垂直轴上的交叉位置。 |
| [DisplayUnit](../../aspose.words.drawing.charts/chartaxis/displayunit/) { get; } | 指定数值轴的显示单位的缩放值。 |
| [Document](../../aspose.words.drawing.charts/chartaxis/document/) { get; } | 返回标题持有者所属的文档。 |
| [Hidden](../../aspose.words.drawing.charts/chartaxis/hidden/) { get; set; } | 获取或设置一个标志，指示该轴是否隐藏。 |
| [MajorTickMark](../../aspose.words.drawing.charts/chartaxis/majortickmark/) { get; set; } | 返回或设置主要刻度线。 |
| [MajorUnit](../../aspose.words.drawing.charts/chartaxis/majorunit/) { get; set; } | 返回或设置主要刻度线之间的距离。 |
| [MajorUnitIsAuto](../../aspose.words.drawing.charts/chartaxis/majorunitisauto/) { get; set; } | 获取或设置一个标志，指示是否应使用主要刻度线之间的默认距离。 |
| [MajorUnitScale](../../aspose.words.drawing.charts/chartaxis/majorunitscale/) { get; set; } | 返回或设置时间类别轴上主要刻度线的刻度值。 |
| [MinorTickMark](../../aspose.words.drawing.charts/chartaxis/minortickmark/) { get; set; } | 返回或设置轴的次刻度线。 |
| [MinorUnit](../../aspose.words.drawing.charts/chartaxis/minorunit/) { get; set; } | 返回或设置小刻度线之间的距离。 |
| [MinorUnitIsAuto](../../aspose.words.drawing.charts/chartaxis/minorunitisauto/) { get; set; } | 获取或设置一个标志，指示是否应使用小刻度线之间的默认距离。 |
| [MinorUnitScale](../../aspose.words.drawing.charts/chartaxis/minorunitscale/) { get; set; } | 返回或设置时间类别轴上小刻度线的刻度值。 |
| [NumberFormat](../../aspose.words.drawing.charts/chartaxis/numberformat/) { get; } | 返回一个[`ChartNumberFormat`](../chartnumberformat/)允许为轴定义数字格式的对象。 |
| [ReverseOrder](../../aspose.words.drawing.charts/chartaxis/reverseorder/) { get; set; } | 返回或设置一个标志，指示轴的值是否应该以相反的顺序显示，即 从最大值到最小值。 |
| [Scaling](../../aspose.words.drawing.charts/chartaxis/scaling/) { get; } | 提供对轴缩放选项的访问。 |
| [TickLabelAlignment](../../aspose.words.drawing.charts/chartaxis/ticklabelalignment/) { get; set; } | 获取或设置轴刻度标签的文本对齐方式。 |
| [TickLabelOffset](../../aspose.words.drawing.charts/chartaxis/ticklabeloffset/) { get; set; } | 获取或设置标签到轴的距离。 |
| [TickLabelPosition](../../aspose.words.drawing.charts/chartaxis/ticklabelposition/) { get; set; } | 返回或设置刻度标签在轴上的位置。 |
| [TickLabelSpacing](../../aspose.words.drawing.charts/chartaxis/ticklabelspacing/) { get; set; } | 获取或设置绘制刻度标签的时间间隔。 |
| [TickLabelSpacingIsAuto](../../aspose.words.drawing.charts/chartaxis/ticklabelspacingisauto/) { get; set; } | 获取或设置一个标志，指示是否应使用绘制刻度标签的自动间隔。 |
| [TickMarkSpacing](../../aspose.words.drawing.charts/chartaxis/tickmarkspacing/) { get; set; } | 获取或设置绘制刻度线的时间间隔。 |
| [Type](../../aspose.words.drawing.charts/chartaxis/type/) { get; } | 返回轴的类型。 |

### 例子

显示如何插入图表并修改其轴的外观。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// 清除图表的演示数据系列以从干净的图表开始。
chart.Series.Clear();

// 插入一个图表系列，其中 X 轴为类别，Y 轴为相应的数值。
chart.Series.Add("Aspose Test Series",
    new[] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 640, 320, 280, 120, 150 });

// 图表轴有各种可以改变其外观的选项，
// 例如它们的方向、主要/次要单位刻度和刻度线。
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Minimum;
xAxis.ReverseOrder = false;
xAxis.MajorTickMark = AxisTickMark.Inside;
xAxis.MinorTickMark = AxisTickMark.Cross;
xAxis.MajorUnit = 10.0d;
xAxis.MinorUnit = 15.0d;
xAxis.TickLabelOffset = 50;
xAxis.TickLabelPosition = AxisTickLabelPosition.Low;
xAxis.TickLabelSpacingIsAuto = false;
xAxis.TickMarkSpacing = 1;

ChartAxis yAxis = chart.AxisY;
yAxis.CategoryType = AxisCategoryType.Automatic;
yAxis.Crosses = AxisCrosses.Maximum;
yAxis.ReverseOrder = true;
yAxis.MajorTickMark = AxisTickMark.Inside;
yAxis.MinorTickMark = AxisTickMark.Cross;
yAxis.MajorUnit = 100.0d;
yAxis.MinorUnit = 20.0d;
yAxis.TickLabelPosition = AxisTickLabelPosition.NextToAxis;

// 柱形图没有 Z 轴。
Assert.Null(chart.AxisZ);

doc.Save(ArtifactsDir + "Charts.AxisProperties.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* 部件 [Aspose.Words](../../)


