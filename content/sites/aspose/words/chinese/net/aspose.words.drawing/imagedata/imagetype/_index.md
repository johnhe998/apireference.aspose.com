---
title: ImageData.ImageType
second_title: Aspose.Words for .NET API 参考
description: ImageData 财产. 获取图像的类型
type: docs
weight: 140
url: /zh/net/aspose.words.drawing/imagedata/imagetype/
---
## ImageData.ImageType property

获取图像的类型。

```csharp
public ImageType ImageType { get; }
```

### 例子

演示如何从文档中提取图像，并将它们作为单独的文件保存到本地文件系统。

```csharp
Document doc = new Document(MyDir + "Images.docx");

// 从文档中获取形状的集合，
// 并将每个形状的图像数据与图像一起作为文件保存到本地文件系统。
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // 形状的图像数据可能包含多种可能的图像格式的图像。 
        // 我们可以根据图像的格式自动确定每个图像的文件扩展名。
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
```

### 也可以看看

* enum [ImageType](../../imagetype/)
* class [ImageData](../)
* 命名空间 [Aspose.Words.Drawing](../../imagedata/)
* 部件 [Aspose.Words](../../../)


