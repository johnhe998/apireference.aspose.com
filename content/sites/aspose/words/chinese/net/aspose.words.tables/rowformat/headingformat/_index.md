---
title: RowFormat.HeadingFormat
second_title: Aspose.Words for .NET API 参考
description: RowFormat 财产. 当表格跨度超过一页时如果该行作为表格标题在每一页上重复则为真
type: docs
weight: 30
url: /zh/net/aspose.words.tables/rowformat/headingformat/
---
## RowFormat.HeadingFormat property

当表格跨度超过一页时，如果该行作为表格标题在每一页上重复，则为真。

```csharp
public bool HeadingFormat { get; set; }
```

### 例子

展示如何构建一个表，其中包含在每一页上重复的行。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();

// 当“HeadingFormat”标志设置为“true”时插入的任何行
// 将显示在它跨越的每个页面的表格顶部。
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Write("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Write("Heading row 2");
builder.EndRow();

builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
builder.RowFormat.HeadingFormat = false;

// 为表格添加足够的行以跨越两页。
for (int i = 0; i < 50; i++)
{
    builder.InsertCell();
    builder.Write($"Row {table.Rows.Count}, column 1.");
    builder.InsertCell();
    builder.Write($"Row {table.Rows.Count}, column 2.");
    builder.EndRow();
}

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableSetHeadingRow.docx");
```

### 也可以看看

* class [RowFormat](../)
* 命名空间 [Aspose.Words.Tables](../../rowformat/)
* 部件 [Aspose.Words](../../../)


