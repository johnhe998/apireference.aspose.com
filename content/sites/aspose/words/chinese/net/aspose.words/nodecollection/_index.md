---
title: Class NodeCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.NodeCollection 班级. 表示特定类型的节点集合
type: docs
weight: 3960
url: /zh/net/aspose.words/nodecollection/
---
## NodeCollection class

表示特定类型的节点集合。

```csharp
public class NodeCollection : IEnumerable<Node>
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | 获取集合中的节点数。 |
| [Item](../../aspose.words/nodecollection/item/) { get; } | 检索给定索引处的节点。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | 将一个节点添加到集合的末尾。 |
| [Clear](../../aspose.words/nodecollection/clear/)() | 从此集合和文档中删除所有节点。 |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | 确定一个节点是否在集合中。 |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | 在节点集合上提供简单的“foreach”样式迭代。 |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | 返回指定节点的从零开始的索引。 |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | 将一个节点插入到集合中指定索引处。 |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | 从集合和文档中删除节点。 |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | 从集合和文档中删除指定索引处的节点。 |
| [ToArray](../../aspose.words/nodecollection/toarray/)() | 将集合中的所有节点复制到新的节点数组中。 |

### 评论

**节点集合**不拥有它包含的节点，而只是指定类型的nodes 的选择，但节点存储在它们各自父节点下的树中。

**节点集合**支持索引访问、迭代并提供添加和删除方法。

这 **节点集合**集合是“实时的”，即对创建它的节点 object 的子节点所做的更改会立即反映在由 **节点集合** 属性和方法。

**节点集合**由返回[`GetChildNodes`](../compositenode/getchildnodes/) 并且还用作类型化节点集合的基类，例如[`SectionCollection`](../sectioncollection/), [`ParagraphCollection`](../paragraphcollection/)等等

**节点集合**可以是“平面的”并且只包含创建它的节点的直接子节点 ，或者它可以是“深的”并且包含所有后代子节点。

### 例子

演示如何用图像形状替换所有文本框形状。

```csharp
Document doc = new Document(MyDir + "Textboxes in drawing canvas.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(3, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(1, shapes.Count(s => s.ShapeType == ShapeType.Image));

foreach (Shape shape in shapes)
{
    if (shape.ShapeType == ShapeType.TextBox)
    {
        Shape replacementShape = new Shape(doc, ShapeType.Image);
        replacementShape.ImageData.SetImage(ImageDir + "Logo.jpg");
        replacementShape.Left = shape.Left;
        replacementShape.Top = shape.Top;
        replacementShape.Width = shape.Width;
        replacementShape.Height = shape.Height;
        replacementShape.RelativeHorizontalPosition = shape.RelativeHorizontalPosition;
        replacementShape.RelativeVerticalPosition = shape.RelativeVerticalPosition;
        replacementShape.HorizontalAlignment = shape.HorizontalAlignment;
        replacementShape.VerticalAlignment = shape.VerticalAlignment;
        replacementShape.WrapType = shape.WrapType;
        replacementShape.WrapSide = shape.WrapSide;

        shape.ParentNode.InsertAfter(replacementShape, shape);
        shape.Remove();
    }
}

shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(0, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(4, shapes.Count(s => s.ShapeType == ShapeType.Image));

doc.Save(ArtifactsDir + "Shape.ReplaceTextboxesWithImages.docx");
```

### 也可以看看

* class [Node](../node/)
* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


