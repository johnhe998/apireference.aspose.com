---
title: Story.Tables
second_title: Aspose.Words for .NET API 参考
description: Story 财产. 获取作为故事直接子级的表的集合
type: docs
weight: 50
url: /zh/net/aspose.words/story/tables/
---
## Story.Tables property

获取作为故事直接子级的表的集合。

```csharp
public TableCollection Tables { get; }
```

### 例子

演示如何删除文档中所有表格的第一行和最后一行。

```csharp
Document doc = new Document(MyDir + "Tables.docx");

TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(5, tables[0].Rows.Count);
Assert.AreEqual(4, tables[1].Rows.Count);

foreach (Table table in tables.OfType<Table>())
{
    table.FirstRow?.Remove();
    table.LastRow?.Remove();
}

Assert.AreEqual(3, tables[0].Rows.Count);
Assert.AreEqual(2, tables[1].Rows.Count);
```

### 也可以看看

* class [TableCollection](../../../aspose.words.tables/tablecollection/)
* class [Story](../)
* 命名空间 [Aspose.Words](../../story/)
* 部件 [Aspose.Words](../../../)


