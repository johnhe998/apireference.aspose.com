---
title: CellFormat.PreferredWidth
second_title: Aspose.Words for .NET API 参考
description: CellFormat 财产. 返回或设置单元格的首选宽度
type: docs
weight: 70
url: /zh/net/aspose.words.tables/cellformat/preferredwidth/
---
## CellFormat.PreferredWidth property

返回或设置单元格的首选宽度。

```csharp
public PreferredWidth PreferredWidth { get; set; }
```

### 评论

首选宽度（连同表格的 Auto Fit 选项）决定了表格布局算法如何计算单元格的实际 宽度。表格布局可以在保存文档时由 Aspose.Words 执行，或在显示文档时由Microsoft Word 执行。

首选宽度可以以磅或百分比指定。首选 width 也可以指定为“auto”，这意味着没有指定首选宽度。

默认值为[`Auto`](../../preferredwidth/auto/).

### 例子

显示如何为表格单元格设置首选宽度。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// 有两种方法可以将“PreferredWidth”类应用于表格单元格。
// 1 - 根据点设置绝对首选宽度：
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - 根据表格宽度的百分比设置相对首选宽度：
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// 没有指定首选宽度的单元格将占用剩余的可用空间。
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// “PreferredWidth”属性的每个配置都会创建一个新对象。
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### 也可以看看

* class [PreferredWidth](../../preferredwidth/)
* class [CellFormat](../)
* 命名空间 [Aspose.Words.Tables](../../cellformat/)
* 部件 [Aspose.Words](../../../)


