---
title: Class TextColumnCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.TextColumnCollection 班级. 集合TextColumn代表文档部分中所有文本列的对象
type: docs
weight: 6100
url: /zh/net/aspose.words/textcolumncollection/
---
## TextColumnCollection class

集合[`TextColumn`](../textcolumn/)代表文档部分中所有文本列的对象。

```csharp
public class TextColumnCollection
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words/textcolumncollection/count/) { get; } | 获取文档部分中的列数。 |
| [EvenlySpaced](../../aspose.words/textcolumncollection/evenlyspaced/) { get; set; } | **真的**如果文本列的宽度相等且间距均匀。 |
| [Item](../../aspose.words/textcolumncollection/item/) { get; } | 返回指定索引处的文本列。 |
| [LineBetween](../../aspose.words/textcolumncollection/linebetween/) { get; set; } | 什么时候 **真的** 在列之间添加一条垂直线。 |
| [Spacing](../../aspose.words/textcolumncollection/spacing/) { get; set; } | 当列均匀分布时，获取或设置每列之间的空间量，以点为单位。 |
| [Width](../../aspose.words/textcolumncollection/width/) { get; } | 当列均匀分布时，获取列的宽度。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [SetCount](../../aspose.words/textcolumncollection/setcount/)(int) | 将文本排列到指定数量的文本列中。 |

### 评论

利用[`SetCount`](./setcount/)设置文本列的数量。

要使所有列的宽度相等且间距均匀，请设置[`EvenlySpaced`](./evenlyspaced/)至 **真的** 并指定列之间的空间量[`Spacing`](./spacing/)MS Word will 自动计算列宽。

如果你有 **均匀分布的**调成 **错误的**，您需要分别为 each 列指定宽度和间距。使用索引器访问个人[`TextColumn`](../textcolumn/)对象。

使用自定义列宽时，请确保所有列宽和它们之间的间距之和 等于页宽减去左右页边距。

### 例子

显示如何在一个部分中创建多个均匀间隔的列。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


