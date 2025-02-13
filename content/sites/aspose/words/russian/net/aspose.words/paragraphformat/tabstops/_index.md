---
title: ParagraphFormat.TabStops
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Получает коллекцию пользовательских позиций табуляции определенных для этого объекта.
type: docs
weight: 380
url: /ru/net/aspose.words/paragraphformat/tabstops/
---
## ParagraphFormat.TabStops property

Получает коллекцию пользовательских позиций табуляции, определенных для этого объекта.

```csharp
public TabStopCollection TabStops { get; }
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

* class [TabStopCollection](../../tabstopcollection/)
* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


