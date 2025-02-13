---
title: ImageSaveOptions.MetafileRenderingOptions
second_title: Aspose.Words for .NET API 参考
description: ImageSaveOptions 财产. 允许指定如何在渲染输出中处理元文件
type: docs
weight: 80
url: /zh/net/aspose.words.saving/imagesaveoptions/metafilerenderingoptions/
---
## ImageSaveOptions.MetafileRenderingOptions property

允许指定如何在渲染输出中处理元文件。

```csharp
public MetafileRenderingOptions MetafileRenderingOptions { get; }
```

### 评论

什么时候Vector指定时，Aspose.Words 先使用自己的元文件渲染引擎将 元文件渲染为矢量图形，然后再将vector 图形渲染为图像。

什么时候Bitmap指定时，Aspose.Words 使用 GDI+ 图元文件渲染引擎直接将 图元文件渲染到图像。

GDI+ 图元文件渲染引擎运行速度更快，支持几乎所有图元文件功能，但与页面上的其余矢量图形（尤其是文本） 相比，低 分辨率可能会产生不一致的结果。 Aspose.Words 元文件渲染引擎将在低分辨率下产生更一致的结果 even 但工作速度较慢并且可能不准确地渲染复杂的元文件。

默认值为[`MetafileRenderingMode`](../../metafilerenderingmode/)是Bitmap.

### 例子

展示了在将带有 Windows Metafile 图像的文档保存为其他图像格式时如何设置呈现模式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(Image.FromFile(ImageDir + "Windows MetaFile.wmf"));

// 当我们将文档保存为图片时，我们可以传递一个 SaveOptions 对象到
// 确定保存操作将如何处理文档中的 Windows 元文件。
// 如果我们将“RenderingMode”属性设置为“MetafileRenderingMode.Vector”，
// 或“MetafileRenderingMode.VectorWithFallback”，我们会将所有元文件渲染为矢量图形。
// 如果我们将“RenderingMode”属性设置为“MetafileRenderingMode.Bitmap”，我们会将所有元文件渲染为位图。
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
options.MetafileRenderingOptions.RenderingMode = metafileRenderingMode;

doc.Save(ArtifactsDir + "ImageSaveOptions.WindowsMetaFile.png", options);
```

### 也可以看看

* class [MetafileRenderingOptions](../../metafilerenderingoptions/)
* class [ImageSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../imagesaveoptions/)
* 部件 [Aspose.Words](../../../)


