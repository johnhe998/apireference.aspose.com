---
title: ShapeBase.SizeInPoints
second_title: Aspose.Words for .NET API 参考
description: ShapeBase 财产. 以点为单位获取形状的大小
type: docs
weight: 470
url: /zh/net/aspose.words.drawing/shapebase/sizeinpoints/
---
## ShapeBase.SizeInPoints property

以点为单位获取形状的大小。

```csharp
public SizeF SizeInPoints { get; }
```

### 例子

显示如何验证形状的大小和标记语言。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ShapeMarkupLanguage.Dml, shape.MarkupLanguage);
Assert.AreEqual(new SizeF(300, 300), shape.SizeInPoints);
```

### 也可以看看

* class [ShapeBase](../)
* 命名空间 [Aspose.Words.Drawing](../../shapebase/)
* 部件 [Aspose.Words](../../../)


