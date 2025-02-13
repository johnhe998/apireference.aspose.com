---
title: DocumentBuilder.DeleteRow
second_title: Aspose.Words for .NET API 参考
description: DocumentBuilder 方法. 从表中删除一行
type: docs
weight: 180
url: /zh/net/aspose.words/documentbuilder/deleterow/
---
## DocumentBuilder.DeleteRow method

从表中删除一行。

```csharp
public Row DeleteRow(int tableIndex, int rowIndex)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| tableIndex | Int32 | 表的索引。 |
| rowIndex | Int32 | 表中行的索引。 |

### 返回值

刚刚删除的行节点。

### 评论

如果游标在要删除的行内，则游标移到 到下一行或表后的下一段。

如果您从只包含一行的表中删除一行，则会删除 whole 表。

对于索引参数，当index大于等于0时，指定从 开始的索引，0为第一个元素。当 index 小于 0 时，它指定一个 index from 结尾， -1 是最后一个元素。

### 例子

显示如何从表中删除一行。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, cell 1.");
builder.InsertCell();
builder.Write("Row 1, cell 2.");
builder.EndRow();
builder.InsertCell();
builder.Write("Row 2, cell 1.");
builder.InsertCell();
builder.Write("Row 2, cell 2.");
builder.EndTable();

Assert.AreEqual(2, table.Rows.Count);

// 删除文档中第一个表的第一行。
builder.DeleteRow(0, 0);

Assert.AreEqual(1, table.Rows.Count);
Assert.AreEqual("Row 2, cell 1.\aRow 2, cell 2.\a\a", table.GetText().Trim());
```

### 也可以看看

* class [Row](../../../aspose.words.tables/row/)
* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)


