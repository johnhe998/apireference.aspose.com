---
title: Class ChartNumberFormat
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Charts.ChartNumberFormat 班级. 表示父元素的数字格式
type: docs
weight: 720
url: /zh/net/aspose.words.drawing.charts/chartnumberformat/
---
## ChartNumberFormat class

表示父元素的数字格式。

```csharp
public class ChartNumberFormat
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [FormatCode](../../aspose.words.drawing.charts/chartnumberformat/formatcode/) { get; set; } | 获取或设置应用于数据标签的格式代码。 |
| [IsLinkedToSource](../../aspose.words.drawing.charts/chartnumberformat/islinkedtosource/) { get; set; } | 指定格式代码是否链接到源单元格。 默认为 true。 |

### 例子

显示如何设置图表值的格式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// 清除图表的演示数据系列以从干净的图表开始。
chart.Series.Clear();

// 将自定义系列添加到图表中，X 轴为类别，
 // 以及 Y 轴的相应大数值。
chart.Series.Add("Aspose Test Series",
    new [] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });

 // 将 Y 轴刻度标签的数字格式设置为不使用逗号分组数字。
chart.AxisY.NumberFormat.FormatCode = "#,##0";

// 这个标志可以覆盖上面的值并从源单元格中绘制数字格式。
Assert.False(chart.AxisY.NumberFormat.IsLinkedToSource);

doc.Save(ArtifactsDir + "Charts.SetNumberFormatToChartAxis.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* 部件 [Aspose.Words](../../)


