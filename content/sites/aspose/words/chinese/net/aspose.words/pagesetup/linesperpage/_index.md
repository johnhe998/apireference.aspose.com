---
title: PageSetup.LinesPerPage
second_title: Aspose.Words for .NET API 参考
description: PageSetup 财产. 获取或设置文档网格中每页的行数
type: docs
weight: 240
url: /zh/net/aspose.words/pagesetup/linesperpage/
---
## PageSetup.LinesPerPage property

获取或设置文档网格中每页的行数。

```csharp
public int LinesPerPage { get; set; }
```

### 评论

该属性的最小值为 1。最大值取决于 Normal 样式的页面高度和字体大小。最小行距是字体大小的 136%。例如， a Letter 页面每页的最大行数为 1 英寸边距为 39。

默认情况下，该属性有一个值，在该值上，行距是 Normal 样式的字体大小的 1.5 倍。

### 例子

显示如何指定每页可能具有的行数限制。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 启用pitching，然后用它来设置本节每页的行数。
// 足够大的字体大小会将一些行向下推到下一页以避免字符重叠。
builder.PageSetup.LayoutMode = SectionLayoutMode.LineGrid;
builder.PageSetup.LinesPerPage = 15;

builder.ParagraphFormat.SnapToGrid = true;

for (int i = 0; i < 30; i++)
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. ");

doc.Save(ArtifactsDir + "PageSetup.LinesPerPage.docx");
```

### 也可以看看

* class [PageSetup](../)
* 命名空间 [Aspose.Words](../../pagesetup/)
* 部件 [Aspose.Words](../../../)


