---
title: ShapeBase.IsMoveFromRevision
second_title: Aspose.Words for .NET API 参考
description: ShapeBase 财产. 返回 真的如果启用更改跟踪时此对象在 Microsoft Word 中被移动删除
type: docs
weight: 310
url: /zh/net/aspose.words.drawing/shapebase/ismovefromrevision/
---
## ShapeBase.IsMoveFromRevision property

返回 **真的**如果启用更改跟踪时此对象在 Microsoft Word 中被移动（删除）。

```csharp
public bool IsMoveFromRevision { get; }
```

### 例子

显示如何识别移动修订形状。

```csharp
// 移动修订是当我们通过在 Microsoft Word 中剪切和粘贴来移动文档正文中的元素，而
// 跟踪变化。如果我们在这样的文本移动中包含一个内联形状，那么该形状也将是一个修订版。
// 复制粘贴或移动浮动形状不会创建移动修订。
Document doc = new Document(MyDir + "Revision shape.docx");

// 移动修订由成对的“Move from”和“Move to”修订组成。我们在这个文件中移动了一个形状，
// 但在我们接受或拒绝移动修订之前，将有两个该形状的实例。
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// 这是“移动到”修订版，即到达目的地的形状。
// 如果我们接受修订，这个“移动到”修订形状将消失，
// 并且“移动自”修订形状将保留。
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// 这是“Move from”修订版，即原始位置的形状。
// 如果我们接受修订，这个“Move from”修订形状将消失，
// 并且“移动到”修订形状将保留。
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

### 也可以看看

* class [ShapeBase](../)
* 命名空间 [Aspose.Words.Drawing](../../shapebase/)
* 部件 [Aspose.Words](../../../)


