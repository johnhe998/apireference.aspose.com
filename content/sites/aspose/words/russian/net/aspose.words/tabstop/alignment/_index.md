---
title: TabStop.Alignment
second_title: Справочник по API Aspose.Words для .NET
description: TabStop свойство. Получает или задает выравнивание текста на этой позиции табуляции.
type: docs
weight: 20
url: /ru/net/aspose.words/tabstop/alignment/
---
## TabStop.Alignment property

Получает или задает выравнивание текста на этой позиции табуляции.

```csharp
public TabAlignment Alignment { get; set; }
```

### Примеры

Показывает, как изменить положение правой позиции табуляции в абзацах, связанных с оглавлением.

```csharp
Document doc = new Document(MyDir + "Table of contents.docx");

// Итерация по всем абзацам со стилями оглавления на основе результатов; это любой стиль между TOC и TOC9.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Получите первую вкладку, используемую в этом абзаце, это должна быть вкладка, используемая для выравнивания номеров страниц.
        TabStop tab = para.ParagraphFormat.TabStops[0];

        // Замените первую вкладку по умолчанию, остановку пользовательской остановкой табуляции.
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }

doc.Save(ArtifactsDir + "Styles.ChangeTocsTabStops.docx");
```

### Смотрите также

* enum [TabAlignment](../../tabalignment/)
* class [TabStop](../)
* пространство имен [Aspose.Words](../../tabstop/)
* сборка [Aspose.Words](../../../)


