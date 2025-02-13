---
title: HtmlSaveOptions.FontsFolderAlias
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定用于构造写入 HTML 文档的字体 URI 的文件夹的名称 默认为空字符串
type: docs
weight: 330
url: /zh/net/aspose.words.saving/htmlsaveoptions/fontsfolderalias/
---
## HtmlSaveOptions.FontsFolderAlias property

指定用于构造写入 HTML 文档的字体 URI 的文件夹的名称。 默认为空字符串。

```csharp
public string FontsFolderAlias { get; set; }
```

### 评论

当你保存一个[`Document`](../../../aspose.words/document/)以 HTML 格式和[`ExportFontResources`](../exportfontresources/) 设置为`真的` Aspose.Words 需要将文档中使用的字体保存为独立文件。 [`FontsFolder`](../fontsfolder/)允许您指定字体的保存位置和 `FontsFolderAlias`允许指定如何构造字体 URI。

如果`FontsFolderAlias`不是空字符串，则字体 URIwritten 到 HTML 将是FontsFolderAlias + &lt;字体文件名&gt;.

如果`FontsFolderAlias`是一个空字符串，那么写入 到 HTML 的字体 URI 将是FontsFolder + &lt;字体文件名&gt;.

如果`FontsFolderAlias`被设定为 '。' （点），那么字体文件名 将被写入没有路径的HTML，无论其他选项如何。

指定文件夹名称以构造字体 URIs 的另一种方法是使用[`ResourceFolderAlias`](../resourcefolderalias/).

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


