---
title: Paragraph.IsFormatRevision
second_title: Справочник по API Aspose.Words для .NET
description: Paragraph свойство. Возвращает значение true если форматирование объекта было изменено в Microsoft Word при включенном отслеживании изменений.
type: docs
weight: 90
url: /ru/net/aspose.words/paragraph/isformatrevision/
---
## Paragraph.IsFormatRevision property

Возвращает значение true, если форматирование объекта было изменено в Microsoft Word при включенном отслеживании изменений.

```csharp
public bool IsFormatRevision { get; }
```

### Примеры

Показывает, как проверить, является ли абзац версией формата.

```csharp
Document doc = new Document(MyDir + "Format revision.docx");

// Этот абзац является исправлением «Формат», которое возникает, когда мы меняем форматирование существующего текста
// при отслеживании редакций в Microsoft Word через "Рецензирование" -> "Отслеживать изменения".
Assert.True(doc.FirstSection.Body.FirstParagraph.IsFormatRevision);
```

### Смотрите также

* class [Paragraph](../)
* пространство имен [Aspose.Words](../../paragraph/)
* сборка [Aspose.Words](../../../)


