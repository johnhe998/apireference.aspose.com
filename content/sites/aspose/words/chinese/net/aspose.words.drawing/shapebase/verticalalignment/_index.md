---
title: ShapeBase.VerticalAlignment
second_title: Aspose.Words for .NET API 参考
description: ShapeBase 财产. 指定形状如何垂直定位
type: docs
weight: 510
url: /zh/net/aspose.words.drawing/shapebase/verticalalignment/
---
## ShapeBase.VerticalAlignment property

指定形状如何垂直定位。

```csharp
public VerticalAlignment VerticalAlignment { get; set; }
```

### 评论

默认值为None.

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

* enum [VerticalAlignment](../../verticalalignment/)
* class [ShapeBase](../)
* 命名空间 [Aspose.Words.Drawing](../../shapebase/)
* 部件 [Aspose.Words](../../../)


