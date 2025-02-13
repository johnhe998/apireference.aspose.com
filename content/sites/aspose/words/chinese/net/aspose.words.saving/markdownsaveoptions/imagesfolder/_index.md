---
title: MarkdownSaveOptions.ImagesFolder
second_title: Aspose.Words for .NET API 参考
description: MarkdownSaveOptions 财产. 指定将文档导出到 时保存图像的物理文件夹Markdown格式默认为空字符串
type: docs
weight: 40
url: /zh/net/aspose.words.saving/markdownsaveoptions/imagesfolder/
---
## MarkdownSaveOptions.ImagesFolder property

指定将文档导出到 时保存图像的物理文件夹Markdown格式。默认为空字符串。

```csharp
public string ImagesFolder { get; set; }
```

### 评论

当你保存一个[`Document`](../../../aspose.words/document/)在Markdown格式， Aspose.Words 需要将文档中嵌入的所有图像保存为独立文件。 `ImagesFolder`允许您指定图像的保存位置。

如果您将文档保存到文件中并提供文件名，Aspose.Words 默认将图像保存在 保存文档文件的同一文件夹中。利用`ImagesFolder`覆盖此行为。

如果将文档保存到流中，Aspose.Words 没有文件夹 用于保存图像，但仍需要将图像保存在某个位置。在这种情况下， 您需要在`ImagesFolder`属性.

如果指定的文件夹由`ImagesFolder`不存在，会自动创建。

### 也可以看看

* class [MarkdownSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../markdownsaveoptions/)
* 部件 [Aspose.Words](../../../)


