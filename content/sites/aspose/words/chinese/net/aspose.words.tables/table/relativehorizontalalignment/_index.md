---
title: Table.RelativeHorizontalAlignment
second_title: Aspose.Words for .NET API 参考
description: Table 财产. 获取或设置浮动表格相对水平对齐方式
type: docs
weight: 230
url: /zh/net/aspose.words.tables/table/relativehorizontalalignment/
---
## Table.RelativeHorizontalAlignment property

获取或设置浮动表格相对水平对齐方式。

```csharp
public HorizontalAlignment RelativeHorizontalAlignment { get; set; }
```

### 例子

显示如何设置浮动表的位置。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 1, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// 将表格的位置设置为页面上的某个位置，例如在本例中为右下角。
table.RelativeVerticalAlignment = VerticalAlignment.Bottom;
table.RelativeHorizontalAlignment = HorizontalAlignment.Right;

table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 2, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// 我们还可以设置从插入表格的段落位置开始的水平和垂直偏移量。 
table.AbsoluteVerticalDistance = 50;
table.AbsoluteHorizontalDistance = 100;

doc.Save(ArtifactsDir + "Table.ChangeFloatingTableProperties.docx");
```

### 也可以看看

* enum [HorizontalAlignment](../../../aspose.words.drawing/horizontalalignment/)
* class [Table](../)
* 命名空间 [Aspose.Words.Tables](../../table/)
* 部件 [Aspose.Words](../../../)


