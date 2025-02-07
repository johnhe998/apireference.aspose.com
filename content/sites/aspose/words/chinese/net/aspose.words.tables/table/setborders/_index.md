---
title: Table.SetBorders
second_title: Aspose.Words for .NET API 参考
description: Table 方法. 将所有表格边框设置为指定的线型宽度和颜色
type: docs
weight: 420
url: /zh/net/aspose.words.tables/table/setborders/
---
## Table.SetBorders method

将所有表格边框设置为指定的线型、宽度和颜色。

```csharp
public void SetBorders(LineStyle lineStyle, double lineWidth, Color color)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| lineStyle | LineStyle | 要应用的线条样式。 |
| lineWidth | Double | 要设置的线宽（以磅为单位）。 |
| color | Color | 用于边框的颜色。 |

### 例子

显示如何一次格式化所有表格的边框。

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// 清除表格中所有现有的边框。
table.ClearBorders();

// 设置一条绿线作为该表的每个外边框和内边框。
table.SetBorders(LineStyle.Single, 1.5, Color.Green);

doc.Save(ArtifactsDir + "Table.SetBorders.docx");
```

展示如何在构建表格时应用边框和底纹颜色。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 启动一个表格并为其边框设置默认颜色/厚度。
Table table = builder.StartTable();
table.SetBorders(LineStyle.Single, 2.0, Color.Black);

// 创建一个包含两个具有不同背景颜色的单元格的行。
builder.InsertCell();
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightSkyBlue;
builder.Writeln("Row 1, Cell 1.");
builder.InsertCell();
builder.CellFormat.Shading.BackgroundPatternColor = Color.Orange;
builder.Writeln("Row 1, Cell 2.");
builder.EndRow();

// 重置单元格格式以禁用背景颜色
// 为构建器创建的所有新单元格设置自定义边框粗细，
// 然后构建第二行。
builder.CellFormat.ClearFormatting();
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;

builder.InsertCell();
builder.Writeln("Row 2, Cell 1.");
builder.InsertCell();
builder.Writeln("Row 2, Cell 2.");

doc.Save(ArtifactsDir + "DocumentBuilder.TableBordersAndShading.docx");
```

### 也可以看看

* enum [LineStyle](../../../aspose.words/linestyle/)
* class [Table](../)
* 命名空间 [Aspose.Words.Tables](../../table/)
* 部件 [Aspose.Words](../../../)


