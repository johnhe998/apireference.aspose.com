---
title: HtmlSaveOptions.ExportOriginalUrlForLinkedImages
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定是否使用原始 URL 作为链接图像的 URL 默认值为错误的.
type: docs
weight: 210
url: /zh/net/aspose.words.saving/htmlsaveoptions/exportoriginalurlforlinkedimages/
---
## HtmlSaveOptions.ExportOriginalUrlForLinkedImages property

指定是否使用原始 URL 作为链接图像的 URL。 默认值为`错误的`.

```csharp
public bool ExportOriginalUrlForLinkedImages { get; set; }
```

### 评论

如果值设置为`真的`[`SourceFullName`](../../../aspose.words.drawing/imagedata/sourcefullname/)value is used 作为链接图像的 URL，并且链接图像未加载到文档的文件夹 或[`ImagesFolder`](../imagesfolder/).

如果值设置为`错误的`链接的图像被加载到文档的 folder 或[`ImagesFolder`](../imagesfolder/)每个链接图像的 URL 是根据文档的文件夹构建的，取决于 ，[`ImagesFolder`](../imagesfolder/) 和[`ImagesFolderAlias`](../imagesfolderalias/)特性。

### 例子

展示如何为 Aspose.Words 在将文档保存为 HTML 时创建的外部保存资源设置文件夹和文件夹别名。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ImageResolution = 72,
    FontResourcesSubsettingSizeThreshold = 0,
    FontsFolder = ArtifactsDir + "Fonts",
    ImagesFolder = ArtifactsDir + "Images",
    ResourceFolder = ArtifactsDir + "Resources",
    FontsFolderAlias = "http://example.com/fonts",
    ImagesFolderAlias = "http://example.com/images",
    ResourceFolderAlias = "http://example.com/resources",
    ExportOriginalUrlForLinkedImages = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.FolderAlias.html", options);
```

### 也可以看看

* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


