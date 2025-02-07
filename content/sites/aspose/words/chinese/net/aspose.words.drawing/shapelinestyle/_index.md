---
title: Enum ShapeLineStyle
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.ShapeLineStyle 枚举. 指定复合线型Shape.
type: docs
weight: 1120
url: /zh/net/aspose.words.drawing/shapelinestyle/
---
## ShapeLineStyle enumeration

指定复合线型[`Shape`](../shape/).

```csharp
public enum ShapeLineStyle
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Single | `0` | 单行。 |
| Double | `1` | 等宽双线。 |
| ThickThin | `2` | 双线，一粗，一细 |
| ThinThick | `3` | 双线，一细一粗。 |
| Triple | `4` | 三条线，细、粗、细。 |
| Default | `0` | 默认值为Single. |

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

* property [LineStyle](../stroke/linestyle/)
* 命名空间 [Aspose.Words.Drawing](../../aspose.words.drawing/)
* 部件 [Aspose.Words](../../)


