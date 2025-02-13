---
title: HtmlSaveOptions.ImageResolution
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定导出为 HTMLMHTML 或 EPUB 时图像的输出分辨率 默认为96 dpi.
type: docs
weight: 350
url: /zh/net/aspose.words.saving/htmlsaveoptions/imageresolution/
---
## HtmlSaveOptions.ImageResolution property

指定导出为 HTML、MHTML 或 EPUB 时图像的输出分辨率。 默认为`96 dpi`.

```csharp
public int ImageResolution { get; set; }
```

### 评论

此属性会在以下情况下影响光栅图像[`ScaleImageToShapeSize`](../scaleimagetoshapesize/) 是`真的`和效果图元文件导出为光栅图像。某些图像属性（例如cropping 或旋转）需要保存转换后的图像，在这种情况下，转换后的图像以 given 分辨率创建。

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

* property [ScaleImageToShapeSize](../scaleimagetoshapesize/)
* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


