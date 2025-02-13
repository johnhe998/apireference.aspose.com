---
title: HtmlSaveOptions.ImagesFolder
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定将文档导出为 HTML 格式时保存图像的物理文件夹 默认为空字符串
type: docs
weight: 370
url: /zh/net/aspose.words.saving/htmlsaveoptions/imagesfolder/
---
## HtmlSaveOptions.ImagesFolder property

指定将文档导出为 HTML 格式时保存图像的物理文件夹。 默认为空字符串。

```csharp
public string ImagesFolder { get; set; }
```

### 评论

当你保存一个[`Document`](../../../aspose.words/document/)在 HTML 格式中，Aspose.Words 需要将文档中嵌入的所有 图像保存为独立文件。`ImagesFolder` 允许您指定图像的保存位置和[`ImagesFolderAlias`](../imagesfolderalias/) 允许指定如何构建图像 URI。

如果您将文档保存到文件中并提供文件名，Aspose.Words 默认将 图像保存在保存文档文件的同一文件夹中。利用`ImagesFolder` 覆盖此行为。

如果您将文档保存到流中，Aspose.Words 没有用于保存图像的文件夹 ，但仍需要将图像保存在某处。在这种情况下，您需要在`ImagesFolder`属性或通过 提供自定义流[`ImageSavingCallback`](../imagesavingcallback/)事件处理程序。

如果指定的文件夹`ImagesFolder`不存在，会自动创建。

[`ResourceFolder`](../resourcefolder/)是另一种指定应保存图像的文件夹的方法。

### 例子

显示保存为 .html 后如何指定用于存储链接图像的文件夹。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

string imagesDir = Path.Combine(ArtifactsDir, "SaveHtmlWithOptions");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

// 设置一个选项以将表单字段导出为纯文本而不是 HTML 输入元素。
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true, 
    ImagesFolder = imagesDir
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveHtmlWithOptions.html", options);
```

### 也可以看看

* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


