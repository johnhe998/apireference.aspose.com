---
title: PdfSaveOptions.PageMode
second_title: Aspose.Words for .NET API 参考
description: PdfSaveOptions 财产. 指定 PDF 文档在 PDF 阅读器中打开时的显示方式
type: docs
weight: 220
url: /zh/net/aspose.words.saving/pdfsaveoptions/pagemode/
---
## PdfSaveOptions.PageMode property

指定 PDF 文档在 PDF 阅读器中打开时的显示方式。

```csharp
public PdfPageMode PageMode { get; set; }
```

### 评论

默认值为UseOutlines.

### 例子

显示如何设置一些 PDF 阅读器在打开输出文档时要遵循的说明。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 将“PageMode”属性设置为“PdfPageMode.FullScreen”，让PDF阅读器打开保存的
// 全屏模式下的文档，它接管了监视器的显示并且没有可见的控件。
// 将“PageMode”属性设置为“PdfPageMode.UseThumbs”，让 PDF 阅读器显示一个单独的面板
// 带有文档中每一页的缩略图。
// 将“PageMode”属性设置为“PdfPageMode.UseOC”，让 PDF 阅读器显示一个单独的面板
// 这允许我们使用文档中存在的任何层。
// 将“PageMode”属性设置为“PdfPageMode.UseOutlines”以获取 PDF 阅读器
// 如果可能，也显示轮廓。
// 将“PageMode”属性设置为“PdfPageMode.UseNone”以使 PDF 阅读器仅显示文档本身。
// 将“PageMode”属性设置为“PdfPageMode.UseAttachments”以使附件面板可见。
options.PageMode = pageMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.PageMode.pdf", options);
```

显示处理我们正在呈现为 PDF 的文档的页眉/页脚中的书签。

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions saveOptions = new PdfSaveOptions();

// 将“PageMode”属性设置为“PdfPageMode.UseOutlines”以在输出 PDF 中显示大纲导航窗格。
saveOptions.PageMode = PdfPageMode.UseOutlines;

// 将“DefaultBookmarksOutlineLevel”属性设置为“1”以显示所有
// 输出 PDF 中大纲第一级的书签。
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// 将“HeaderFooterBookmarksExportMode”属性设置为“HeaderFooterBookmarksExportMode.None”以
// 不导出页眉/页脚内的任何书签。
// 将“HeaderFooterBookmarksExportMode”属性设置为“HeaderFooterBookmarksExportMode.First”
// 仅在第一部分的页眉/页脚中导出书签。
// 将“HeaderFooterBookmarksExportMode”属性设置为“HeaderFooterBookmarksExportMode.All”以
// 导出所有页眉/页脚中的书签。
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### 也可以看看

* enum [PdfPageMode](../../pdfpagemode/)
* class [PdfSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pdfsaveoptions/)
* 部件 [Aspose.Words](../../../)


