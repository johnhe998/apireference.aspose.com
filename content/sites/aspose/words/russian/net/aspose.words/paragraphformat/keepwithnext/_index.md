---
title: ParagraphFormat.KeepWithNext
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Истинно если абзац должен оставаться на той же странице что и следующий за ним абзац.
type: docs
weight: 160
url: /ru/net/aspose.words/paragraphformat/keepwithnext/
---
## ParagraphFormat.KeepWithNext property

Истинно, если абзац должен оставаться на той же странице, что и следующий за ним абзац.

```csharp
public bool KeepWithNext { get; set; }
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

* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


