---
title: HtmlSaveOptions.FontsFolder
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定将文档导出为 HTML 时保存字体的物理文件夹 默认为空字符串
type: docs
weight: 320
url: /zh/net/aspose.words.saving/htmlsaveoptions/fontsfolder/
---
## HtmlSaveOptions.FontsFolder property

指定将文档导出为 HTML 时保存字体的物理文件夹。 默认为空字符串。

```csharp
public string FontsFolder { get; set; }
```

### 评论

当你保存一个[`Document`](../../../aspose.words/document/)以 HTML 格式和[`ExportFontResources`](../exportfontresources/) 设置为`真的` Aspose.Words 需要将文档中使用的字体保存为独立文件。 `FontsFolder`允许您指定字体的保存位置和 [`FontsFolderAlias`](../fontsfolderalias/)允许指定如何构造字体 URI。

如果您将文档保存到文件中并提供文件名，Aspose.Words 默认将 字体保存在保存文档文件的同一文件夹中。利用`FontsFolder` 覆盖此行为。

如果您将文档保存到流中，Aspose.Words 没有保存字体的文件夹， 但仍需要将字体保存在某处。在这种情况下，您需要在`FontsFolder`属性或通过 提供自定义流[`FontSavingCallback`](../fontsavingcallback/)事件处理程序。

如果指定的文件夹`FontsFolder`不存在，会自动创建。

[`ResourceFolder`](../resourcefolder/)是另一种指定应保存字体的文件夹的方法。

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


