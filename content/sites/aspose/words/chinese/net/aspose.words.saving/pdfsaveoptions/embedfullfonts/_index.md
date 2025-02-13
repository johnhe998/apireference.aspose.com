---
title: PdfSaveOptions.EmbedFullFonts
second_title: Aspose.Words for .NET API 参考
description: PdfSaveOptions 财产. 控制字体如何嵌入到生成的 PDF 文档中
type: docs
weight: 100
url: /zh/net/aspose.words.saving/pdfsaveoptions/embedfullfonts/
---
## PdfSaveOptions.EmbedFullFonts property

控制字体如何嵌入到生成的 PDF 文档中。

```csharp
public bool EmbedFullFonts { get; set; }
```

### 评论

默认值为`错误的`，这意味着在嵌入之前对字体进行子集化。 如果要保持输出文件更小，子集化很有用。子集从字体中删除 all 未使用的字形。

当此值设置为`真的`，一个完整的字体文件被嵌入到 PDF 中，没有 子集。这将导致更大的输出文件，但当您想要 稍后编辑生成的 PDF（例如添加更多文本）时，这可能是一个有用的选项。

一些字体很大（几兆字节）并且在没有 subsetting 的情况下嵌入它们会导致输出文档很大。

### 例子

演示如何在将文档呈现为 PDF 时嵌入字体时启用或禁用子集。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Arvo";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// 配置我们的字体源以确保我们可以访问本文档中的两种字体。
FontSourceBase[] originalFontsSources = FontSettings.DefaultInstance.GetFontsSources();
Aspose.Words.Fonts.FolderFontSource folderFontSource = new Aspose.Words.Fonts.FolderFontSource(FontsDir, true);
FontSettings.DefaultInstance.SetFontsSources(new[] { originalFontsSources[0], folderFontSource });

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(fontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 由于我们的文档包含自定义字体，因此可能需要嵌入到输出文档中。
// 将“EmbedFullFonts”属性设置为“true”以在输出 PDF 中嵌入每个嵌入字体的每个字形。
// 文档的大小可能会变得非常大，但如果我们编辑 PDF，我们将充分利用所有字体。
// 将“EmbedFullFonts”属性设置为“false”以对字体应用子集，只保存字形
// 文档正在使用。文件会小很多，
// 但如果我们编辑文档，我们可能需要访问任何自定义字体。
options.EmbedFullFonts = embedFullFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf", options);

if (embedFullFonts)
    Assert.That(500000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));
else
    Assert.That(25000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));

// 恢复原始字体源。
FontSettings.DefaultInstance.SetFontsSources(originalFontsSources);
```

### 也可以看看

* class [PdfSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pdfsaveoptions/)
* 部件 [Aspose.Words](../../../)


