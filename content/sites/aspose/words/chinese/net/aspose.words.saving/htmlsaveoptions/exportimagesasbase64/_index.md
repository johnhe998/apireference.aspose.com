---
title: HtmlSaveOptions.ExportImagesAsBase64
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定图像是否以 Base64 格式保存到输出 HTMLMHTML 或 EPUB 默认为错误的.
type: docs
weight: 180
url: /zh/net/aspose.words.saving/htmlsaveoptions/exportimagesasbase64/
---
## HtmlSaveOptions.ExportImagesAsBase64 property

指定图像是否以 Base64 格式保存到输出 HTML、MHTML 或 EPUB。 默认为`错误的`.

```csharp
public bool ExportImagesAsBase64 { get; set; }
```

### 评论

当此属性设置为`真的`图像数据直接导出到  **图像**不会创建元素和单独的文件。

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


