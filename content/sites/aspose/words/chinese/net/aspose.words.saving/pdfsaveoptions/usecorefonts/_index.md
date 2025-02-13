---
title: PdfSaveOptions.UseCoreFonts
second_title: Aspose.Words for .NET API 参考
description: PdfSaveOptions 财产. 获取或设置一个值确定是否将 TrueType 字体 ArialTimes New Roman Courier New 和 Symbol 替换为核心 PDF Type 1 字体
type: docs
weight: 280
url: /zh/net/aspose.words.saving/pdfsaveoptions/usecorefonts/
---
## PdfSaveOptions.UseCoreFonts property

获取或设置一个值，确定是否将 TrueType 字体 Arial、Times New Roman、 Courier New 和 Symbol 替换为核心 PDF Type 1 字体。

```csharp
public bool UseCoreFonts { get; set; }
```

### 评论

默认值为`错误的` .当此值设置为`真的`Arial、Times New Roman、 Courier New 和 Symbol 字体在 PDF 文档中被替换为对应的核心 Type 1 字体。

any PDF 查看器应用程序需要核心 PDF 字体或其字体规格和合适的替代字体。

此设置仅适用于 ANSI (Windows-1252) 编码的文本。无论此设置如何，非 ANSI 文本都将使用嵌入的 TrueType 字体写入 。

PDF/A 和 PDF/UA 合规性要求嵌入所有字体。`错误的`保存到 PDF/A 和 PDF/UA 时，值将自动使用 。

保存为 PDF 2.0 格式时不支持核心字体。`错误的`保存到 PDF 2.0 时，值将自动使用 。

此选项具有更高的优先级[`FontEmbeddingMode`](../fontembeddingmode/)选项。

### 例子

显示如何启用/禁用 PDF Type 1 字体替换。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 将“UseCoreFonts”属性设置为“true”以替换一些字体，
// 包括我们文档中的两种字体，以及它们的 PDF Type 1 等价物。
// 将“UseCoreFonts”属性设置为“false”以不应用 PDF Type 1 字体。
options.UseCoreFonts = useCoreFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf", options);

if (useCoreFonts)
    Assert.That(3000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
else
    Assert.That(30000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
```

### 也可以看看

* class [PdfSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pdfsaveoptions/)
* 部件 [Aspose.Words](../../../)


