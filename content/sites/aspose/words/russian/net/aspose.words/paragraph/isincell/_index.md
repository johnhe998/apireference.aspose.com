---
title: Paragraph.IsInCell
second_title: Справочник по API Aspose.Words для .NET
description: Paragraph свойство. Истинно если этот абзац является непосредственным потомкомCell  false иначе.
type: docs
weight: 100
url: /ru/net/aspose.words/paragraph/isincell/
---
## Paragraph.IsInCell property

Истинно, если этот абзац является непосредственным потомком[`Cell`](../../../aspose.words.tables/cell/) ; false иначе.

```csharp
public bool IsInCell { get; }
```

### Примеры

Показывает, как накрыть стол, чтобы оставаться вместе на одной странице.

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Включение KeepWithNext для каждого абзаца в таблице, кроме
// последние в последней строке предотвратят разбиение таблицы на несколько страниц.
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### Смотрите также

* class [Paragraph](../)
* пространство имен [Aspose.Words](../../paragraph/)
* сборка [Aspose.Words](../../../)


