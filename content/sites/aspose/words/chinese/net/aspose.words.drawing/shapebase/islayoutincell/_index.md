---
title: ShapeBase.IsLayoutInCell
second_title: Aspose.Words for .NET API 参考
description: ShapeBase 财产. 获取或设置一个标志指示形状是显示在表格内还是表格外
type: docs
weight: 300
url: /zh/net/aspose.words.drawing/shapebase/islayoutincell/
---
## ShapeBase.IsLayoutInCell property

获取或设置一个标志，指示形状是显示在表格内还是表格外。

```csharp
public bool IsLayoutInCell { get; set; }
```

### 评论

默认值为 **真的**.

仅对顶层形状有效，属性[`WrapType`](../wraptype/)其中设置为 value 以外[`Inline`](../../../aspose.words/inline/).

### 例子

演示如何确定如何在表格单元格中显示形状。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.InsertCell();
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.BottomPadding = 20;
tableStyle.LeftPadding = 10;
tableStyle.RightPadding = 10;
tableStyle.TopPadding = 20;
tableStyle.Borders.Color = Color.Black;
tableStyle.Borders.LineStyle = LineStyle.Single;

table.Style = tableStyle;

builder.MoveTo(table.FirstRow.FirstCell.FirstParagraph);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 50,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);

// 将“IsLayoutInCell”属性设置为“true”以将形状显示为单元格段落内的内联元素。
// 将确定形状位置的坐标原点将是形状单元格的左上角。
// 如果我们重新调整单元格的大小，形状将从单元格的左上角开始移动以保持相同的位置。
// 将“IsLayoutInCell”属性设置为“false”，将形状显示为独立的浮动形状。
// 将确定形状位置的坐标原点将是页面的左上角，
// 并且形状不会响应其单元格的任何重新调整大小。
shape.IsLayoutInCell = isLayoutInCell;

// 我们只能将“IsLayoutInCell”属性应用于浮动形状。
shape.WrapType = WrapType.None;

doc.Save(ArtifactsDir + "Shape.LayoutInTableCell.docx");
```

### 也可以看看

* class [ShapeBase](../)
* 命名空间 [Aspose.Words.Drawing](../../shapebase/)
* 部件 [Aspose.Words](../../../)


