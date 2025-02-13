---
title: Paragraph.IsEndOfCell
second_title: Aspose.Words for .NET API 参考
description: Paragraph 财产. 如果本段是最后一段则为真Cell否则为假
type: docs
weight: 50
url: /zh/net/aspose.words/paragraph/isendofcell/
---
## Paragraph.IsEndOfCell property

如果本段是最后一段，则为真[`Cell`](../../../aspose.words.tables/cell/);否则为假。

```csharp
public bool IsEndOfCell { get; }
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

* class [Paragraph](../)
* 命名空间 [Aspose.Words](../../paragraph/)
* 部件 [Aspose.Words](../../../)


