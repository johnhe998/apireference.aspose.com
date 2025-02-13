---
title: HtmlSaveOptions.ExportHeadersFootersMode
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定页眉和页脚如何输出到 HTMLMHTML 或 EPUB 默认值为PerSection对于 HTML/MHTML 和None对于 EPUB.
type: docs
weight: 170
url: /zh/net/aspose.words.saving/htmlsaveoptions/exportheadersfootersmode/
---
## HtmlSaveOptions.ExportHeadersFootersMode property

指定页眉和页脚如何输出到 HTML、MHTML 或 EPUB。 默认值为PerSection对于 HTML/MHTML 和None对于 EPUB.

```csharp
public ExportHeadersFootersMode ExportHeadersFootersMode { get; set; }
```

### 评论

很难将页眉和页脚有意义地输出到 HTML，因为 HTML 没有分页。

当这个属性是PerSectionAspose.Words exports 仅在每个部分的开头和结尾处的主要页眉和页脚。

几时FirstSectionHeaderLastSectionFooter 仅导出第一个主页眉和最后一个主页脚（包括链接到上一个）。

您可以通过将此 property 设置为来完全禁用页眉和页脚的导出None.

### 例子

演示如何在将文档保存为 HTML 时省略页眉/页脚。

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// 此文档包含页眉和页脚。我们可以通过“HeadersFooters”集合访问它们。
Assert.AreEqual("First header", doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderFirst].GetText().Trim());

// .html 等格式不会将文档拆分为页面，因此页眉/页脚的功能不会相同
// 当我们使用 Microsoft Word 将文档打开为 .docx 时，它们会这样做。
// 如果我们将带有页眉/页脚的文档转换为 html，则转换会将页眉/页脚同化为正文。
// 我们可以使用 SaveOptions 对象在转换为 html 时省略页眉/页脚。
HtmlSaveOptions saveOptions =
    new HtmlSaveOptions(SaveFormat.Html) { ExportHeadersFootersMode = ExportHeadersFootersMode.None };

doc.Save(ArtifactsDir + "HeaderFooter.ExportMode.html", saveOptions);

// 打开我们保存的文档并验证它不包含标题的文本
doc = new Document(ArtifactsDir + "HeaderFooter.ExportMode.html");

Assert.IsFalse(doc.Range.Text.Contains("First header"));
```

### 也可以看看

* enum [ExportHeadersFootersMode](../../exportheadersfootersmode/)
* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


