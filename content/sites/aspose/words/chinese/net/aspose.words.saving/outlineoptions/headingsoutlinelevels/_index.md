---
title: OutlineOptions.HeadingsOutlineLevels
second_title: Aspose.Words for .NET API 参考
description: OutlineOptions 财产. 指定要包含在 文档大纲中的标题级别以标题样式格式化的段落
type: docs
weight: 70
url: /zh/net/aspose.words.saving/outlineoptions/headingsoutlinelevels/
---
## OutlineOptions.HeadingsOutlineLevels property

指定要包含在 文档大纲中的标题级别（以标题样式格式化的段落）。

```csharp
public int HeadingsOutlineLevels { get; set; }
```

### 评论

指定 0 表示大纲中没有标题；为大纲中的一级标题指定 1，依此类推。

默认值为 0。有效范围为 0 到 9。

### 例子

演示如何将整个文档转换为文档大纲中具有三个级别的 PDF。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入级别 1 到 5 的标题。
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;

builder.Writeln("Heading 1.2.2.1");
builder.Writeln("Heading 1.2.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.2.2.2.1");
builder.Writeln("Heading 1.2.2.2.2");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 输出的 PDF 文档将包含一个大纲，它是一个目录，列出了文档正文中的标题。
// 单击此大纲中的条目会将我们带到其各自标题的位置。
// 将“HeadingsOutlineLevels”属性设置为“4”，从大纲中排除所有级别高于4的标题。
options.OutlineOptions.HeadingsOutlineLevels = 4;

// 如果一个大纲条目在其自身和下一个相同或更低级别的条目之间有更高级别的后续条目，
// 条目左侧会出现一个箭头。这个条目是几个这样的“子条目”的“所有者”。
// 在我们的文档中，第 5 级标题的大纲条目是第二个 4 级大纲条目的子条目，
 // 第 4 和第 5 级标题条目是第二个 3 级条目的子条目，依此类推。
// 在大纲中，我们可以单击“所有者”条目的箭头来折叠/展开其所有子条目。
// 将“ExpandedOutlineLevels”属性设置为“2”以自动展开所有标题级别 2 和更低的大纲条目
// 并在我们打开文档时折叠所有级别和 3 及更高级别的条目。
options.OutlineOptions.ExpandedOutlineLevels = 2;

doc.Save(ArtifactsDir + "PdfSaveOptions.ExpandedOutlineLevels.pdf", options);
```

### 也可以看看

* class [OutlineOptions](../)
* 命名空间 [Aspose.Words.Saving](../../outlineoptions/)
* 部件 [Aspose.Words](../../../)


