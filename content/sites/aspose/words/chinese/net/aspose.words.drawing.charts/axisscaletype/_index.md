---
title: Enum AxisScaleType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Charts.AxisScaleType 枚举. 指定轴的可能比例类型
type: docs
weight: 550
url: /zh/net/aspose.words.drawing.charts/axisscaletype/
---
## AxisScaleType enumeration

指定轴的可能比例类型。

```csharp
public enum AxisScaleType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Linear | `0` | 线性缩放。 |
| Logarithmic | `1` | 对数缩放。 |

### 例子

显示如何将对数缩放应用于图表轴。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape chartShape = builder.InsertChart(ChartType.Scatter, 450, 300);
Chart chart = chartShape.Chart;

// 清除图表的演示数据系列以从干净的图表开始。
chart.Series.Clear();

// 为五个点插入一个带有 X/Y 坐标的系列。
chart.Series.Add("Series 1", 
    new[] { 1.0, 2.0, 3.0, 4.0, 5.0 }, 
    new[] { 1.0, 20.0, 400.0, 8000.0, 160000.0 });

// X轴的缩放默认是线性的，
// 显示覆盖 X 值范围 (0, 1, 2, 3...) 的均匀递增值。
// 线性轴不适合我们的 Y 值
// 因为 Y 值较小的点将更难阅读。
// 以 20 为底的对数缩放 (1, 20, 400, 8000...)
// 将散布绘制的点，使我们能够更轻松地在图表上读取它们的值。
chart.AxisY.Scaling.Type = AxisScaleType.Logarithmic;
chart.AxisY.Scaling.LogBase = 20;

doc.Save(ArtifactsDir + "Charts.AxisScaling.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* 部件 [Aspose.Words](../../)


