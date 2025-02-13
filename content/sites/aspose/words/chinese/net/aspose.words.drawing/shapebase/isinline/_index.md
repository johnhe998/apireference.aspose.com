---
title: ShapeBase.IsInline
second_title: Aspose.Words for .NET API 参考
description: ShapeBase 财产. 一种快速确定此形状是否与文本内联的方法
type: docs
weight: 280
url: /zh/net/aspose.words.drawing/shapebase/isinline/
---
## ShapeBase.IsInline property

一种快速确定此形状是否与文本内联的方法。

```csharp
public bool IsInline { get; }
```

### 评论

仅对顶级形状有效。

### 例子

显示如何确定形状是内联的还是浮动的。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 下面是形状可能具有的两种包装类型。
// 1 - 内联：
builder.Write("Hello world! ");
Shape shape = builder.InsertShape(ShapeType.Rectangle, 100, 100);
shape.FillColor = Color.LightBlue;
builder.Write(" Hello again.");

// 内联形状位于其他段落元素（例如文本运行）中的段落内。
// 在 Microsoft Word 中，我们可以单击并将形状拖动到任何段落，就好像它是一个字符一样。
// 如果形状很大，会影响垂直段落间距。
// 我们不能将此形状移动到没有段落的地方。
Assert.AreEqual(WrapType.Inline, shape.WrapType);
Assert.True(shape.IsInline);

// 2 - 浮动：
shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin ,200, 
    RelativeVerticalPosition.TopMargin ,200, 100, 100, WrapType.None);
shape.FillColor = Color.Orange;

// 一个浮动形状属于我们插入它的段落，
// 我们可以通过单击形状时出现的锚符号来确定。
// 如果形状左侧没有可见的锚符号，
// 我们需要通过“选项”启用可见锚点 -> “显示”-> “对象锚”。
// 在 Microsoft Word 中，我们可以左键单击并将此形状自由拖动到任何位置。
Assert.AreEqual(WrapType.None, shape.WrapType);
Assert.False(shape.IsInline);

doc.Save(ArtifactsDir + "Shape.IsInline.docx");
```

### 也可以看看

* class [ShapeBase](../)
* 命名空间 [Aspose.Words.Drawing](../../shapebase/)
* 部件 [Aspose.Words](../../../)


