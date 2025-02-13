---
title: SvgSaveOptions.ResourcesFolder
second_title: Aspose.Words for .NET API 参考
description: SvgSaveOptions 财产. 指定将文档导出为 Svg 格式时保存资源图像的物理文件夹 默认为无效的.
type: docs
weight: 50
url: /zh/net/aspose.words.saving/svgsaveoptions/resourcesfolder/
---
## SvgSaveOptions.ResourcesFolder property

指定将文档导出为 Svg 格式时保存资源（图像）的物理文件夹。 默认为`无效的`.

```csharp
public string ResourcesFolder { get; set; }
```

### 评论

仅在以下情况下有效[`ExportEmbeddedImages`](../exportembeddedimages/)属性为假。

当你保存一个[`Document`](../../../aspose.words/document/)在 SVG 格式中，Aspose.Words 需要将文档中嵌入的所有 图像保存为独立文件。`ResourcesFolder` 允许您指定图像的保存位置和[`ResourcesFolderAlias`](../resourcesfolderalias/) 允许指定如何构建图像 URI。

如果您将文档保存到文件中并提供文件名，Aspose.Words 默认将 图像保存在保存文档文件的同一文件夹中。利用`ResourcesFolder` 覆盖此行为。

如果您将文档保存到流中，Aspose.Words 没有用于保存图像的文件夹 ，但仍需要将图像保存在某处。在这种情况下，您需要在`ResourcesFolder`财产

### 例子

演示如何操作和打印在将文档转换为 .svg 时创建的链接资源的 URI。

```csharp
public void SvgResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    SvgSaveOptions options = new SvgSaveOptions
    {
        SaveFormat = SaveFormat.Svg,
        ExportEmbeddedImages = false,
        ResourcesFolder = ArtifactsDir + "SvgResourceFolder",
        ResourcesFolderAlias = ArtifactsDir + "SvgResourceFolderAlias",
        ShowPageBorder = false,

        ResourceSavingCallback = new ResourceUriPrinter()
    };

    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "SvgSaveOptions.SvgResourceFolder.svg", options);
}

/// <summary>
/// 在转换为 .svg 时计算并打印包含的资源的 URI。
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Console.WriteLine($"Resource #{++mSavedResourceCount} \"{args.ResourceFileName}\"");
        Console.WriteLine("\t" + args.ResourceFileUri);
    }

    private int mSavedResourceCount;
}
```

### 也可以看看

* class [SvgSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../svgsaveoptions/)
* 部件 [Aspose.Words](../../../)


