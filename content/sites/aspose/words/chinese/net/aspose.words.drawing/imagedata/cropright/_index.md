---
title: ImageData.CropRight
second_title: Aspose.Words for .NET API 参考
description: ImageData 财产. 定义图片从右侧移除的分数
type: docs
weight: 80
url: /zh/net/aspose.words.drawing/imagedata/cropright/
---
## ImageData.CropRight property

定义图片从右侧移除的分数。

```csharp
public double CropRight { get; set; }
```

### 评论

裁剪量的范围可以从 -1.0 到 1.0。默认值为 0。注意 值 1 将根本不显示任何图片。负值将导致 图片从被裁剪的边缘向内挤压（图片和裁剪边缘之间的空白空间 将由 形状的填充颜色填充）。小于 1 的正值将导致剩余的图片被 拉伸以适应形状。

默认值为 0。

### 例子

显示如何编辑形状的图像数据。

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");
Shape sourceShape = (Shape)imgSourceDoc.GetChildNodes(NodeType.Shape, true)[0];

Document dstDoc = new Document();

// 从源文档中导入一个形状并将其附加到第一段。
Shape importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

// 导入的形状包含一个图像。我们可以通过 ImageData 对象访问图像的属性和原始数据。
ImageData imageData = importedShape.ImageData;
imageData.Title = "Imported Image";

Assert.True(imageData.HasImage);

// 如果图像没有边框，它的 ImageData 对象将定义边框颜色为空。
Assert.AreEqual(4, imageData.Borders.Count);
Assert.AreEqual(Color.Empty, imageData.Borders[0].Color);

// 此图像未链接到本地文件系统中的另一个形状或图像文件。
Assert.False(imageData.IsLink);
Assert.False(imageData.IsLinkOnly);

// “亮度”和“对比度”属性定义图像亮度和对比度
// 在 0-1 范围内，默认值为 0.5。
imageData.Brightness = 0.8;
imageData.Contrast = 1.0;

// 上面的亮度和对比度值创建了一个有很多白色的图像。
// 我们可以用 ChromaKey 属性选择一种颜色来替换为透明度，比如白色。
imageData.ChromaKey = Color.White;

// 再次导入源形状并将图像设置为单色。
importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

importedShape.ImageData.GrayScale = true;

// 再次导入源形状以创建第三个图像并将其设置为 BiLevel。
// BiLevel 将每个像素设置为黑色或白色，以更接近原始颜色为准。
importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

importedShape.ImageData.BiLevel = true;

// 裁剪以 0-1 的比例确定。将一侧裁剪 0.3
// 将在裁剪侧裁剪 30% 的图像。
importedShape.ImageData.CropBottom = 0.3;
importedShape.ImageData.CropLeft = 0.3;
importedShape.ImageData.CropTop = 0.3;
importedShape.ImageData.CropRight = 0.3;

dstDoc.Save(ArtifactsDir + "Drawing.ImageData.docx");
```

### 也可以看看

* class [ImageData](../)
* 命名空间 [Aspose.Words.Drawing](../../imagedata/)
* 部件 [Aspose.Words](../../../)


