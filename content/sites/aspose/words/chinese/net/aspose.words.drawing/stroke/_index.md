---
title: Class Stroke
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Stroke 班级. 定义形状的笔触
type: docs
weight: 1160
url: /zh/net/aspose.words.drawing/stroke/
---
## Stroke class

定义形状的笔触。

```csharp
public class Stroke
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [BackColor](../../aspose.words.drawing/stroke/backcolor/) { get; set; } | 获取或设置描边的背景颜色。 |
| [Color](../../aspose.words.drawing/stroke/color/) { get; set; } | 定义笔画的颜色。 |
| [Color2](../../aspose.words.drawing/stroke/color2/) { get; set; } | 定义笔画的第二种颜色。 |
| [DashStyle](../../aspose.words.drawing/stroke/dashstyle/) { get; set; } | 指定笔划的点划线图案。 |
| [EndArrowLength](../../aspose.words.drawing/stroke/endarrowlength/) { get; set; } | 定义笔画末端的箭头长度。 |
| [EndArrowType](../../aspose.words.drawing/stroke/endarrowtype/) { get; set; } | 定义笔画末端的箭头。 |
| [EndArrowWidth](../../aspose.words.drawing/stroke/endarrowwidth/) { get; set; } | 定义笔画末端的箭头宽度。 |
| [EndCap](../../aspose.words.drawing/stroke/endcap/) { get; set; } | 定义笔画末端的笔帽样式。 |
| [ForeColor](../../aspose.words.drawing/stroke/forecolor/) { get; set; } | 获取或设置描边的前景色。 |
| [ImageBytes](../../aspose.words.drawing/stroke/imagebytes/) { get; } | 为描边图像或图案填充定义图像。 |
| [JoinStyle](../../aspose.words.drawing/stroke/joinstyle/) { get; set; } | 定义多段线的连接样式。 |
| [LineStyle](../../aspose.words.drawing/stroke/linestyle/) { get; set; } | 定义描边的线型。 |
| [On](../../aspose.words.drawing/stroke/on/) { get; set; } | 定义路径是否会被描边。 |
| [Opacity](../../aspose.words.drawing/stroke/opacity/) { get; set; } | 定义描边的透明度。有效范围是从 0 到 1. |
| [StartArrowLength](../../aspose.words.drawing/stroke/startarrowlength/) { get; set; } | 定义笔划起点的箭头长度。 |
| [StartArrowType](../../aspose.words.drawing/stroke/startarrowtype/) { get; set; } | 定义笔画开始的箭头。 |
| [StartArrowWidth](../../aspose.words.drawing/stroke/startarrowwidth/) { get; set; } | 定义笔划起点的箭头宽度。 |
| [Transparency](../../aspose.words.drawing/stroke/transparency/) { get; set; } | 获取或设置一个介于 0.0（不透明）和 1.0（透明）之间的值，表示描边的透明度 。 |
| [Visible](../../aspose.words.drawing/stroke/visible/) { get; set; } | 获取或设置指示笔划是否可见的标志。 |
| [Weight](../../aspose.words.drawing/stroke/weight/) { get; set; } | 以点为单位定义描边形状路径的画笔厚度。 |

### 评论

使用[`Stroke`](../shape/stroke/)属性来访问形状的笔触属性。 您不创建的实例`Stroke`直接上课。

### 例子

显示如何更改笔触属性。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);

// 基本形状，例如矩形，有两个可见部分。
// 1 - 填充，应用于形状轮廓内的区域：
shape.Fill.ForeColor = Color.White;

// 2 - 描边，标记形状的轮廓：
// 修改这个形状的笔画的各种属性。
Stroke stroke = shape.Stroke;
stroke.On = true;
stroke.Weight = 5;
stroke.Color = Color.Red;
stroke.DashStyle = DashStyle.ShortDashDotDot;
stroke.JoinStyle = JoinStyle.Miter;
stroke.EndCap = EndCap.Square;
stroke.LineStyle = ShapeLineStyle.Triple;

doc.Save(ArtifactsDir + "Shape.Stroke.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Drawing](../../aspose.words.drawing/)
* 部件 [Aspose.Words](../../)


