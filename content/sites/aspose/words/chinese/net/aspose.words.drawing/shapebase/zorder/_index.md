---
title: ShapeBase.ZOrder
second_title: Aspose.Words for .NET API 参考
description: ShapeBase 财产. 确定重叠形状的显示顺序
type: docs
weight: 550
url: /zh/net/aspose.words.drawing/shapebase/zorder/
---
## ShapeBase.ZOrder property

确定重叠形状的显示顺序。

```csharp
public int ZOrder { get; set; }
```

### 评论

仅对顶级形状有效。

默认值为 0。

数字代表堆叠优先级。具有较大数字的形状将显示 ，就好像它与具有较低数字的形状重叠（在“前面”）。

重叠形状的顺序与文档标题和 main 文本中的形状无关。

组形状中子形状的显示顺序由它们在组形状中的 order 决定。

### 例子

显示如何操作形状的顺序。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入三个相互部分重叠的不同颜色的矩形。
// 当我们插入一个与另一个形状重叠的形状时，Aspose.Words 将新形状放在旧形状之上。
// 浅绿色矩形将与浅蓝色矩形重叠并部分遮挡它，
// 浅蓝色矩形会遮住橙色矩形。
Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);
shape.FillColor = Color.Orange;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 150,
    RelativeVerticalPosition.TopMargin, 150, 200, 200, WrapType.None);
shape.FillColor = Color.LightBlue;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 200,
    RelativeVerticalPosition.TopMargin, 200, 200, 200, WrapType.None);
shape.FillColor = Color.LightGreen;

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

// 形状的“ZOrder”属性决定了它在其他重叠形状中的堆叠优先级。
// 如果两个重叠的形状有不同的“ZOrder”值，
 // Microsoft Word 会将具有较高值的形状放在具有较低值的形状之上。
// 设置形状的“ZOrder”值，将第一个橙色矩形放在第二个浅蓝色矩形上
// 和第三个浅绿色矩形上方的第二个浅蓝色矩形。
// 这将颠倒它们原来的堆叠顺序。
shapes[0].ZOrder = 3;
shapes[1].ZOrder = 2;
shapes[2].ZOrder = 1;

doc.Save(ArtifactsDir + "Shape.ZOrder.docx");
```

### 也可以看看

* class [ShapeBase](../)
* 命名空间 [Aspose.Words.Drawing](../../shapebase/)
* 部件 [Aspose.Words](../../../)


