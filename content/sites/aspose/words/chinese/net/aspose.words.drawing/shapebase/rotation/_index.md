---
title: ShapeBase.Rotation
second_title: Aspose.Words for .NET API 参考
description: ShapeBase 财产. 定义形状旋转的角度以度为单位 正值对应于顺时针旋转角度
type: docs
weight: 430
url: /zh/net/aspose.words.drawing/shapebase/rotation/
---
## ShapeBase.Rotation property

定义形状旋转的角度（以度为单位）。 正值对应于顺时针旋转角度。

```csharp
public double Rotation { get; set; }
```

### 评论

默认值为 0。

### 例子

显示如何插入和旋转图像。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入带有图像的形状。
Shape shape = builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
Assert.True(shape.CanHaveImage);
Assert.True(shape.HasImage);

// 将图像顺时针旋转 45 度。
shape.Rotation = 45;

doc.Save(ArtifactsDir + "Shape.Rotate.docx");
```

### 也可以看看

* class [ShapeBase](../)
* 命名空间 [Aspose.Words.Drawing](../../shapebase/)
* 部件 [Aspose.Words](../../../)


