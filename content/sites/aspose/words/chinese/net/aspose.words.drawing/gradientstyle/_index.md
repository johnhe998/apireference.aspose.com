---
title: Enum GradientStyle
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.GradientStyle 枚举. 指定渐变填充的样式
type: docs
weight: 870
url: /zh/net/aspose.words.drawing/gradientstyle/
---
## GradientStyle enumeration

指定渐变填充的样式。

```csharp
public enum GradientStyle
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| None | `-1` | 没有渐变。 |
| Horizontal | `1` | 在对象上水平运行的渐变。 |
| Vertical | `2` | 沿对象垂直向下的渐变。 |
| DiagonalUp | `3` | 从底角向上移动到对角的对角梯度。 |
| DiagonalDown | `4` | 从顶角向下移动到对角的对角梯度。 |
| FromCorner | `5` | 从一个角到其他三个角的渐变。 |
| FromCenter | `6` | 从中心到角落的渐变。 |

### 例子

展示如何用渐变填充形状。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// 使用渐变填充的 ForeColor 对形状应用单色渐变填充。
shape.Fill.OneColorGradient(Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2, 0.1);

Assert.AreEqual(Color.Red.ToArgb(), shape.Fill.ForeColor.ToArgb());
Assert.AreEqual(GradientStyle.Horizontal, shape.Fill.GradientStyle);
Assert.AreEqual(GradientVariant.Variant2, shape.Fill.GradientVariant);
Assert.AreEqual(270, shape.Fill.GradientAngle);

shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// 对形状应用双色渐变填充。
shape.Fill.TwoColorGradient(GradientStyle.FromCorner, GradientVariant.Variant4);
// 改变渐变填充的背景颜色。
shape.Fill.BackColor = Color.Yellow;
// 注意将“GradientAngle”更改为“GradientStyle.FromCorner/GradientStyle.FromCenter”
// 渐变填充没有任何效果，它只适用于线性渐变。
shape.Fill.GradientAngle = 15;

Assert.AreEqual(Color.Yellow.ToArgb(), shape.Fill.BackColor.ToArgb());
Assert.AreEqual(GradientStyle.FromCorner, shape.Fill.GradientStyle);
Assert.AreEqual(GradientVariant.Variant4, shape.Fill.GradientVariant);
Assert.AreEqual(0, shape.Fill.GradientAngle);

// 如果您想获得“GradientStyle”，请使用合规性选项使用 DML 定义形状，
// 文档保存后的“GradientVariant”和“GradientAngle”属性。
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientFill.docx", saveOptions);
```

### 也可以看看

* 命名空间 [Aspose.Words.Drawing](../../aspose.words.drawing/)
* 部件 [Aspose.Words](../../)


