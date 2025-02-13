---
title: ShapeBase.RelativeHorizontalPosition
second_title: Aspose.Words for .NET API 参考
description: ShapeBase 财产. 指定相对于水平位置的形状
type: docs
weight: 400
url: /zh/net/aspose.words.drawing/shapebase/relativehorizontalposition/
---
## ShapeBase.RelativeHorizontalPosition property

指定相对于水平位置的形状。

```csharp
public RelativeHorizontalPosition RelativeHorizontalPosition { get; set; }
```

### 评论

默认值为Column.

仅对顶级浮动形状有效。

### 例子

演示如何将浮动图像插入页面中心。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入将出现在重叠文本后面的浮动图像，并将其与页面中心对齐。
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### 也可以看看

* enum [RelativeHorizontalPosition](../../relativehorizontalposition/)
* class [ShapeBase](../)
* 命名空间 [Aspose.Words.Drawing](../../shapebase/)
* 部件 [Aspose.Words](../../../)


