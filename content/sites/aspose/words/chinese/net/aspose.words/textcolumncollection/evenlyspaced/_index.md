---
title: TextColumnCollection.EvenlySpaced
second_title: Aspose.Words for .NET API 参考
description: TextColumnCollection 财产. 真的如果文本列的宽度相等且间距均匀
type: docs
weight: 20
url: /zh/net/aspose.words/textcolumncollection/evenlyspaced/
---
## TextColumnCollection.EvenlySpaced property

**真的**如果文本列的宽度相等且间距均匀。

```csharp
public bool EvenlySpaced { get; set; }
```

### 例子

显示如何创建不均匀间隔的列。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
PageSetup pageSetup = builder.PageSetup;

TextColumnCollection columns = pageSetup.TextColumns;
columns.EvenlySpaced = false;
columns.SetCount(2);

// 确定我们可用于排列列的空间量。
double contentWidth = pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin;

Assert.AreEqual(470.30d, contentWidth, 0.01d);

// 将第一列设置为窄。
TextColumn column = columns[0];
column.Width = 100;
column.SpaceAfter = 20;

// 将第二列设置为占用页面边缘内剩余的可用空间。
column = columns[1];
column.Width = contentWidth - column.Width - column.SpaceAfter;

builder.Writeln("Narrow column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Wide column 2.");

doc.Save(ArtifactsDir + "PageSetup.CustomColumnWidth.docx");
```

### 也可以看看

* class [TextColumnCollection](../)
* 命名空间 [Aspose.Words](../../textcolumncollection/)
* 部件 [Aspose.Words](../../../)


