---
title: ParagraphFormat.PageBreakBefore
second_title: Aspose.Words for .NET API 参考
description: ParagraphFormat 财产. 如果在段落之前强制分页则为真
type: docs
weight: 250
url: /zh/net/aspose.words/paragraphformat/pagebreakbefore/
---
## ParagraphFormat.PageBreakBefore property

如果在段落之前强制分页，则为真。

```csharp
public bool PageBreakBefore { get; set; }
```

### 例子

演示如何创建开头带有分页符的段落。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 将此标志设置为“true”以在每个段落的开头应用分页符
// 文档构建器将在此 ParagraphFormat 配置下创建。
// 第一段不会收到分页符。
// 将此标志保留为“false”以在同一页面上开始每个新段落
// 和前面一样，只要有足够的空间。
builder.ParagraphFormat.PageBreakBefore = pageBreakBefore;

builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

LayoutCollector layoutCollector = new LayoutCollector(doc);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

if (pageBreakBefore)
{
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[0]));
    Assert.AreEqual(2, layoutCollector.GetStartPageIndex(paragraphs[1]));
}
else
{
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[0]));
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[1]));
}

doc.Save(ArtifactsDir + "ParagraphFormat.PageBreakBefore.docx");
```

### 也可以看看

* class [ParagraphFormat](../)
* 命名空间 [Aspose.Words](../../paragraphformat/)
* 部件 [Aspose.Words](../../../)


