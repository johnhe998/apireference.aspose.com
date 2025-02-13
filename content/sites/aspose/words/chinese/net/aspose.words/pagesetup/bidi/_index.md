---
title: PageSetup.Bidi
second_title: Aspose.Words for .NET API 参考
description: PageSetup 财产. 指定此部分包含双向复杂脚本文本
type: docs
weight: 10
url: /zh/net/aspose.words/pagesetup/bidi/
---
## PageSetup.Bidi property

指定此部分包含双向（复杂脚本）文本。

```csharp
public bool Bidi { get; set; }
```

### 评论

如果为 true，则此部分中的列从右到左排列。

### 例子

显示如何设置部分中文本列的顺序。

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TextColumns.SetCount(3);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Write("Column 2.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Write("Column 3.");

// 将“Bidi”属性设置为“true”以从页面右侧开始排列列。
// 列的顺序将匹配从右到左文本的方向。
// 将“Bidi”属性设置为“false”以从页面左侧开始排列列。
// 列的顺序将匹配从左到右文本的方向。
pageSetup.Bidi = reverseColumns;

doc.Save(ArtifactsDir + "PageSetup.Bidi.docx");
```

### 也可以看看

* class [PageSetup](../)
* 命名空间 [Aspose.Words](../../pagesetup/)
* 部件 [Aspose.Words](../../../)


