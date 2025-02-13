---
title: Row.EnsureMinimum
second_title: Aspose.Words for .NET API 参考
description: Row 方法. 如果 排没有单元格创建并附加一个 细胞.
type: docs
weight: 110
url: /zh/net/aspose.words.tables/row/ensureminimum/
---
## Row.EnsureMinimum method

如果 **排**没有单元格，创建并附加一个 **细胞**.

```csharp
public void EnsureMinimum()
```

### 例子

展示如何确保行节点包含我们开始向其添加内容所需的节点。

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
Row row = new Row(doc);
table.AppendChild(row);

// 行包含单元格，包含具有典型元素的段落，例如运行、形状甚至其他表格。
// 我们的新行没有这些节点，我们不能在它添加内容之前添加内容。
Assert.AreEqual(0, row.GetChildNodes(NodeType.Any, true).Count);

// 在表上调用“EnsureMinimum”方法将确保
// 表格至少有一个单元格包含一个空段落。
row.EnsureMinimum();
row.FirstCell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### 也可以看看

* class [Row](../)
* 命名空间 [Aspose.Words.Tables](../../row/)
* 部件 [Aspose.Words](../../../)


