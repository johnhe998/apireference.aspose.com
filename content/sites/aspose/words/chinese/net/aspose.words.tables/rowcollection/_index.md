---
title: Class RowCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Tables.RowCollection 班级. 提供对集合的类型化访问Row节点.
type: docs
weight: 6020
url: /zh/net/aspose.words.tables/rowcollection/
---
## RowCollection class

提供对集合的类型化访问[`Row`](../row/)节点.

```csharp
public class RowCollection : NodeCollection
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | 获取集合中的节点数。 |
| [Item](../../aspose.words.tables/rowcollection/item/) { get; } | 检索一个 **排**在给定的索引处。 (2 indexers) |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | 将一个节点添加到集合的末尾。 |
| [Clear](../../aspose.words/nodecollection/clear/)() | 从此集合和文档中删除所有节点。 |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | 确定一个节点是否在集合中。 |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | 在节点集合上提供简单的“foreach”样式迭代。 |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | 返回指定节点的从零开始的索引。 |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | 将一个节点插入到集合中指定索引处。 |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | 从集合和文档中删除节点。 |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | 从集合和文档中删除指定索引处的节点。 |
| [ToArray](../../aspose.words.tables/rowcollection/toarray/#toarray_1)() | 将集合中的所有行复制到新的行数组中。 (2 methods) |

### 例子

展示如何遍历文档中的所有表格并打印每个单元格的内容。

```csharp
Document doc = new Document(MyDir + "Tables.docx");
TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(2, tables.ToArray().Length);

for (int i = 0; i < tables.Count; i++)
{
    Console.WriteLine($"Start of Table {i}");

    RowCollection rows = tables[i].Rows;

    // 我们可以在行集合上使用“ToArray”方法将其克隆到数组中。
    Assert.AreEqual(rows, rows.ToArray());
    Assert.AreNotSame(rows, rows.ToArray());

    for (int j = 0; j < rows.Count; j++)
    {
        Console.WriteLine($"\tStart of Row {j}");

        CellCollection cells = rows[j].Cells;

        // 我们可以在单元格集合上使用“ToArray”方法将其克隆到数组中。
        Assert.AreEqual(cells, cells.ToArray());
        Assert.AreNotSame(cells, cells.ToArray());

        for (int k = 0; k < cells.Count; k++)
        {
            string cellText = cells[k].ToString(SaveFormat.Text).Trim();
            Console.WriteLine($"\t\tContents of Cell:{k} = \"{cellText}\"");
        }

        Console.WriteLine($"\tEnd of Row {j}");
    }

    Console.WriteLine($"End of Table {i}\n");
}
```

### 也可以看看

* class [NodeCollection](../../aspose.words/nodecollection/)
* 命名空间 [Aspose.Words.Tables](../../aspose.words.tables/)
* 部件 [Aspose.Words](../../)


