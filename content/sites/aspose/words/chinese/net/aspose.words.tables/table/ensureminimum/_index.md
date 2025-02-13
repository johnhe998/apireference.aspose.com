---
title: Table.EnsureMinimum
second_title: Aspose.Words for .NET API 参考
description: Table 方法. 如果表没有行创建并追加一个 排.
type: docs
weight: 400
url: /zh/net/aspose.words.tables/table/ensureminimum/
---
## Table.EnsureMinimum method

如果表没有行，创建并追加一个 **排**.

```csharp
public void EnsureMinimum()
```

### 例子

展示了如何确保一个表节点包含我们需要添加内容的节点。

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);

// 表格包含行，其中包含单元格，其中可能包含段落
// 带有典型元素，例如运行、形状，甚至其他表格。
// 我们的新表没有这些节点，在它出现之前我们不能向它添加内容。
Assert.AreEqual(0, table.GetChildNodes(NodeType.Any, true).Count);

// 在表上调用“EnsureMinimum”方法将确保
// 表格至少有一行和一个单元格有一个空段落。
table.EnsureMinimum();
table.FirstRow.FirstCell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### 也可以看看

* class [Table](../)
* 命名空间 [Aspose.Words.Tables](../../table/)
* 部件 [Aspose.Words](../../../)


