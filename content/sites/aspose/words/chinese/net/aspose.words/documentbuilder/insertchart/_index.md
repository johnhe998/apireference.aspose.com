---
title: DocumentBuilder.InsertChart
second_title: Aspose.Words for .NET API 参考
description: DocumentBuilder 方法. 在文档中插入一个图表对象并将其缩放到指定的大小
type: docs
weight: 260
url: /zh/net/aspose.words/documentbuilder/insertchart/
---
## InsertChart(ChartType, double, double) {#insertchart_1}

在文档中插入一个图表对象并将其缩放到指定的大小。

```csharp
public Shape InsertChart(ChartType chartType, double width, double height)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| chartType | ChartType | 要插入到文档中的图表类型。 |
| width | Double | 图像的宽度（以磅为单位）。可以是负值或零值以请求 100% 比例。 |
| height | Double | 图像的高度（以磅为单位）。可以是负值或零值以请求 100% 比例。 |

### 返回值

刚刚插入的图像节点。

### 评论

您可以使用 更改图像大小、位置、定位方法和其他设置[`Shape`](../../../aspose.words.drawing/shape/)此方法返回的对象。

### 例子

显示如何将饼图插入到文档中。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Pie, ConvertUtil.PixelToPoint(300), 
    ConvertUtil.PixelToPoint(300)).Chart;
chart.Series.Add("My fruit",
    new[] { "Apples", "Bananas", "Cherries" },
    new[] { 1.3, 2.2, 1.5 });

doc.Save(ArtifactsDir + "DocumentBuilder.InsertPieChart.docx");
```

### 也可以看看

* class [Shape](../../../aspose.words.drawing/shape/)
* enum [ChartType](../../../aspose.words.drawing.charts/charttype/)
* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)

---

## InsertChart(ChartType, RelativeHorizontalPosition, double, RelativeVerticalPosition, double, double, double, WrapType) {#insertchart}

在文档中插入一个图表对象并将其缩放到指定的大小。

```csharp
public Shape InsertChart(ChartType chartType, RelativeHorizontalPosition horzPos, double left, 
    RelativeVerticalPosition vertPos, double top, double width, double height, WrapType wrapType)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| chartType | ChartType | 要插入到文档中的图表类型。 |
| horzPos | RelativeHorizontalPosition | 指定从何处测量到图像的距离。 |
| left | Double | 从原点到图像左侧的距离（以点为单位）。 |
| vertPos | RelativeVerticalPosition | 指定从何处测量到图像的距离。 |
| top | Double | 从原点到图像顶部的距离（以点为单位）。 |
| width | Double | 图像的宽度（以磅为单位）。可以是负值或零值以请求 100% 比例。 |
| height | Double | 图像的高度（以磅为单位）。可以是负值或零值以请求 100% 比例。 |
| wrapType | WrapType | 指定如何在图像周围环绕文本。 |

### 返回值

刚刚插入的图像节点。

### 评论

您可以使用 更改图像大小、位置、定位方法和其他设置[`Shape`](../../../aspose.words.drawing/shape/)此方法返回的对象。

### 例子

显示如何在插入图表时指定位置和换行。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertChart(ChartType.Pie, RelativeHorizontalPosition.Margin, 100, RelativeVerticalPosition.Margin,
    100, 200, 100, WrapType.Square);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertedChartRelativePosition.docx");
```

### 也可以看看

* class [Shape](../../../aspose.words.drawing/shape/)
* enum [ChartType](../../../aspose.words.drawing.charts/charttype/)
* enum [RelativeHorizontalPosition](../../../aspose.words.drawing/relativehorizontalposition/)
* enum [RelativeVerticalPosition](../../../aspose.words.drawing/relativeverticalposition/)
* enum [WrapType](../../../aspose.words.drawing/wraptype/)
* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)


