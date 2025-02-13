---
title: PageSetup.LayoutMode
second_title: Aspose.Words for .NET API 参考
description: PageSetup 财产. 获取或设置本节的布局模式
type: docs
weight: 190
url: /zh/net/aspose.words/pagesetup/layoutmode/
---
## PageSetup.LayoutMode property

获取或设置本节的布局模式。

```csharp
public SectionLayoutMode LayoutMode { get; set; }
```

### 例子

显示如何为每行可能包含的字符数指定 a。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 启用间距，然后使用它来设置本节中每行的字符数。
builder.PageSetup.LayoutMode = SectionLayoutMode.Grid;
builder.PageSetup.CharactersPerLine = 10;

// 字符数还取决于字体的大小。
doc.Styles["Normal"].Font.Size = 20;

Assert.AreEqual(8, doc.FirstSection.PageSetup.CharactersPerLine);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "PageSetup.CharactersPerLine.docx");
```

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

* enum [SectionLayoutMode](../../sectionlayoutmode/)
* class [PageSetup](../)
* 命名空间 [Aspose.Words](../../pagesetup/)
* 部件 [Aspose.Words](../../../)


