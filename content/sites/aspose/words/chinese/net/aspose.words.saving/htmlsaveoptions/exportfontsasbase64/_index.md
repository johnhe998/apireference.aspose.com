---
title: HtmlSaveOptions.ExportFontsAsBase64
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定字体资源是否应该以 Base64 编码嵌入到 HTML 默认为错误的.
type: docs
weight: 160
url: /zh/net/aspose.words.saving/htmlsaveoptions/exportfontsasbase64/
---
## HtmlSaveOptions.ExportFontsAsBase64 property

指定字体资源是否应该以 Base64 编码嵌入到 HTML。 默认为`错误的`.

```csharp
public bool ExportFontsAsBase64 { get; set; }
```

### 评论

默认情况下，字体被写入单独的文件。如果此选项设置为`真的`，字体将以 Base64 编码嵌入到文档的 CSS 中。

### 例子

展示如何在已保存的 HTML 文档中嵌入字体。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportFontsAsBase64 = true,
    CssStyleSheetType = CssStyleSheetType.Embedded,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportFontsAsBase64.html", options);
```

展示如何保存嵌入了图像的 .html 文档。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportImagesAsBase64 = exportImagesAsBase64,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportImagesAsBase64.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportImagesAsBase64.html");

Assert.True(exportImagesAsBase64
    ? outDocContents.Contains("<img src=\"data:image/png;base64")
    : outDocContents.Contains("<img src=\"HtmlSaveOptions.ExportImagesAsBase64.001.png\""));
```

### 也可以看看

* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


