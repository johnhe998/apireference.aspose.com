---
title: Section.AppendContent
second_title: Справочник по API Aspose.Words для .NET
description: Section метод. Вставляет копию содержимого исходного раздела в конец этого раздела.
type: docs
weight: 80
url: /ru/net/aspose.words/section/appendcontent/
---
## Section.AppendContent method

Вставляет копию содержимого исходного раздела в конец этого раздела.

```csharp
public void AppendContent(Section sourceSection)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| sourceSection | Section | Раздел, из которого копируется содержимое. |

### Примечания

Только содержание[`Body`](../body/) исходного раздела копируется, настройки страницы, верхние и нижние колонтитулы не копируются.

Узлы автоматически импортируются, если исходный раздел принадлежит другому документу.

В целевом документе не создается новый раздел.

### Примеры

Показывает, как добавить содержимое раздела в другой раздел.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 3");

Section section = doc.Sections[2];

Assert.AreEqual("Section 3" + ControlChar.SectionBreak, section.GetText());

// Вставляем содержимое первого раздела в начало третьего раздела.
Section sectionToPrepend = doc.Sections[0];
section.PrependContent(sectionToPrepend);

// Вставляем содержимое второго раздела в конец третьего раздела.
Section sectionToAppend = doc.Sections[1];
section.AppendContent(sectionToAppend);

// Методы "PrependContent" и "AppendContent" не создали новых секций.
Assert.AreEqual(3, doc.Sections.Count);
Assert.AreEqual("Section 1" + ControlChar.ParagraphBreak +
                "Section 3" + ControlChar.ParagraphBreak +
                "Section 2" + ControlChar.SectionBreak, section.GetText());
```

### Смотрите также

* class [Section](../)
* пространство имен [Aspose.Words](../../section/)
* сборка [Aspose.Words](../../../)


