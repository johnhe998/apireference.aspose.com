---
title: Shape.TextBox
second_title: Aspose.Words for .NET API 参考
description: Shape 财产. 定义指定文本如何在形状中显示的属性
type: docs
weight: 220
url: /zh/net/aspose.words.drawing/shape/textbox/
---
## Shape.TextBox property

定义指定文本如何在形状中显示的属性。

```csharp
public TextBox TextBox { get; }
```

### 例子

演示如何设置文本框内的文本方向。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// 将文档构建器移动到 TextBox 内部并添加文本。
builder.MoveTo(textBoxShape.LastParagraph);
builder.Writeln("Hello world!");
builder.Write("Hello again!");

// 设置“LayoutFlow”属性以设置此文本框文本内容的方向。
textBox.LayoutFlow = layoutFlow;

doc.Save(ArtifactsDir + "Shape.TextBoxLayoutFlow.docx");
```

### 也可以看看

* class [TextBox](../../textbox/)
* class [Shape](../)
* 命名空间 [Aspose.Words.Drawing](../../shape/)
* 部件 [Aspose.Words](../../../)


