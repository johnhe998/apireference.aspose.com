---
title: Row.IsLastRow
second_title: Aspose.Words for .NET API 参考
description: Row 财产. 如果这是表中的最后一行则为真否则为假
type: docs
weight: 50
url: /zh/net/aspose.words.tables/row/islastrow/
---
## Row.IsLastRow property

如果这是表中的最后一行，则为真；否则为假。

```csharp
public bool IsLastRow { get; }
```

### 例子

显示如何设置表格以保持在同一页面上。

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// 为表格中的每个段落启用 KeepWithNext，除了
// 最后一行中的最后一个将防止表拆分为多个页面。
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### 也可以看看

* class [Row](../)
* 命名空间 [Aspose.Words.Tables](../../row/)
* 部件 [Aspose.Words](../../../)


