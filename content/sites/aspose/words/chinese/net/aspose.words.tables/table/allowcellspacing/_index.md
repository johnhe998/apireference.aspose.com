---
title: Table.AllowCellSpacing
second_title: Aspose.Words for .NET API 参考
description: Table 财产. 获取或设置允许单元格之间的间距选项
type: docs
weight: 60
url: /zh/net/aspose.words.tables/table/allowcellspacing/
---
## Table.AllowCellSpacing property

获取或设置“允许单元格之间的间距”选项。

```csharp
public bool AllowCellSpacing { get; set; }
```

### 例子

显示如何在表格中的各个单元格之间启用间距。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Animal");
builder.InsertCell();
builder.Write("Class");
builder.EndRow();
builder.InsertCell();
builder.Write("Dog");
builder.InsertCell();
builder.Write("Mammal");
builder.EndTable();

table.CellSpacing = 3;

// 将“AllowCellSpacing”属性设置为“true”以启用单元格之间的间距
// 大小等于“CellSpacing”属性的值，以磅为单位。
// 将“AllowCellSpacing”属性设置为“false”以禁用单元格间距
// 并忽略“CellSpacing”属性的值。
table.AllowCellSpacing = allowCellSpacing;

doc.Save(ArtifactsDir + "Table.AllowCellSpacing.html");

// 调整“CellSpacing”属性将自动启用单元格间距。
table.CellSpacing = 5;

Assert.True(table.AllowCellSpacing);
```

### 也可以看看

* class [Table](../)
* 命名空间 [Aspose.Words.Tables](../../table/)
* 部件 [Aspose.Words](../../../)


