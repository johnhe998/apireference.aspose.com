---
title: Class HeaderFooterCollection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.HeaderFooterCollection сорт. Предоставляет типизированный доступ кHeaderFooter узлы Раздел .
type: docs
weight: 2930
url: /ru/net/aspose.words/headerfootercollection/
---
## HeaderFooterCollection class

Предоставляет типизированный доступ к[`HeaderFooter`](../headerfooter/) узлы **Раздел** .

```csharp
public class HeaderFooterCollection : NodeCollection
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Получает количество узлов в коллекции. |
| [Item](../../aspose.words/headerfootercollection/item/) { get; } | Получает **Верхний колонтитул** по данному индексу. (3 indexers) |

## Методы

| Имя | Описание |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | Добавляет узел в конец коллекции. |
| [Clear](../../aspose.words/nodecollection/clear/)() | Удаляет все узлы из этой коллекции и из документа. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | Определяет, находится ли узел в коллекции. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | Обеспечивает простую итерацию в стиле foreach по набору узлов. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | Возвращает отсчитываемый от нуля индекс указанного узла. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | Вставляет узел в коллекцию по указанному индексу. |
| [LinkToPrevious](../../aspose.words/headerfootercollection/linktoprevious/#linktoprevious_1)(bool) | Связывает или разъединяет все верхние и нижние колонтитулы с соответствующими верхними и нижними колонтитулами в предыдущем разделе. |
| [LinkToPrevious](../../aspose.words/headerfootercollection/linktoprevious/#linktoprevious)(HeaderFooterType, bool) | Связывает или разъединяет указанный верхний или нижний колонтитул с соответствующим верхним или нижним колонтитулом в предыдущем разделе. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | Удаляет узел из коллекции и из документа. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | Удаляет узел с указанным индексом из коллекции и из документа. |
| [ToArray](../../aspose.words/headerfootercollection/toarray/#toarray)() | Копирует все`ЗаголовокFooter` s из коллекции в новый массив`ЗаголовокFooter` с. (2 methods) |

### Примечания

Может быть максимум один **Верхний колонтитул**

каждого[`HeaderFooterType`](../headerfootertype/) per  **Раздел** .

**Верхний колонтитул** объекты могут встречаться в коллекции в любом порядке.

### Примеры

Показывает, как удалить все нижние колонтитулы из документа.

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// Перебираем каждый раздел и удаляем нижние колонтитулы всех видов.
foreach (Section section in doc.OfType<Section>())
{
    // Существует три типа нижнего и верхнего колонтитула.
    // 1 - «Первый» верхний/нижний колонтитул, который появляется только на первой странице раздела.
    HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
    footer?.Remove();

    // 2 - «Основной» верхний/нижний колонтитул, который появляется на нечетных страницах.
    footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
    footer?.Remove();

     // 3 - "Четный" верхний/нижний колонтитул, который появляется на четных страницах.
    footer = section.HeadersFooters[HeaderFooterType.FooterEven];
    footer?.Remove();

    Assert.AreEqual(0, section.HeadersFooters.Count(hf => !((HeaderFooter)hf).IsHeader));
}

doc.Save(ArtifactsDir + "HeaderFooter.RemoveFooters.docx");
```

Показывает, как создать верхний и нижний колонтитулы.

```csharp
Document doc = new Document();

// Создаем заголовок и добавляем к нему абзац. Текст в этом абзаце
// появится в верхней части каждой страницы этого раздела над основным текстом.
HeaderFooter header = new HeaderFooter(doc, HeaderFooterType.HeaderPrimary);
doc.FirstSection.HeadersFooters.Add(header);

Paragraph para = header.AppendParagraph("My header.");

Assert.True(header.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

// Создаем нижний колонтитул и добавляем к нему абзац. Текст в этом абзаце
// появится внизу каждой страницы этого раздела, под основным текстом.
HeaderFooter footer = new HeaderFooter(doc, HeaderFooterType.FooterPrimary);
doc.FirstSection.HeadersFooters.Add(footer);

para = footer.AppendParagraph("My footer.");

Assert.False(footer.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

Assert.AreEqual(footer, para.ParentStory);
Assert.AreEqual(footer.ParentSection, para.ParentSection);
Assert.AreEqual(footer.ParentSection, header.ParentSection);

doc.Save(ArtifactsDir + "HeaderFooter.Create.docx");
```

### Смотрите также

* class [NodeCollection](../nodecollection/)
* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


