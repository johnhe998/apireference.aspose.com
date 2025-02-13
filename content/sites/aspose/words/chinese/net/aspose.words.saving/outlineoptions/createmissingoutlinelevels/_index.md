---
title: OutlineOptions.CreateMissingOutlineLevels
second_title: Aspose.Words for .NET API 参考
description: OutlineOptions 财产. 获取或设置一个值该值确定在 导出文档时是否创建缺少的大纲级别
type: docs
weight: 30
url: /zh/net/aspose.words.saving/outlineoptions/createmissingoutlinelevels/
---
## OutlineOptions.CreateMissingOutlineLevels property

获取或设置一个值，该值确定在 导出文档时是否创建缺少的大纲级别。

此属性的默认值为 **错误的**.

```csharp
public bool CreateMissingOutlineLevels { get; set; }
```

### 例子

演示如何在保存 PDF 文档时使用不包含任何相应标题的大纲级别。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入可作为 1 级和 5 级 TOC 条目的标题。
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.1.1.1.1");
builder.Writeln("Heading 1.1.1.1.2");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions saveOptions = new PdfSaveOptions();

// 输出的 PDF 文档将包含一个大纲，它是一个目录，列出了文档正文中的标题。
// 单击此大纲中的条目会将我们带到其各自标题的位置。
// 将“HeadingsOutlineLevels”属性设置为“5”，以在大纲中包含所有级别 5 及以下的标题。
saveOptions.OutlineOptions.HeadingsOutlineLevels = 5;

 // 此文档包含 1 级和 5 级的标题，没有 2、3 和 4 级的标题。
// 输出的 PDF 文档会将大纲级别 2、3 和 4 视为“缺失”。
// 将“CreateMissingOutlineLevels”属性设置为“true”以在大纲中包含所有缺失的级别，
// 因为没有可用的标题，所以留下空白的大纲条目。
// 将“CreateMissingOutlineLevels”属性设置为“false”以忽略缺少的大纲级别，
// 并将大纲级别 5 的标题视为级别 2。
saveOptions.OutlineOptions.CreateMissingOutlineLevels = createMissingOutlineLevels;

doc.Save(ArtifactsDir + "PdfSaveOptions.CreateMissingOutlineLevels.pdf", saveOptions);
```

### 也可以看看

* class [OutlineOptions](../)
* 命名空间 [Aspose.Words.Saving](../../outlineoptions/)
* 部件 [Aspose.Words](../../../)


