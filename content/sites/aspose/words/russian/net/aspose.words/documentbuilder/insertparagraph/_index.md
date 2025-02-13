---
title: DocumentBuilder.InsertParagraph
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder метод. Вставляет разрыв абзаца в документ.
type: docs
weight: 400
url: /ru/net/aspose.words/documentbuilder/insertparagraph/
---
## DocumentBuilder.InsertParagraph method

Вставляет разрыв абзаца в документ.

```csharp
public Paragraph InsertParagraph()
```

### Возвращаемое значение

Только что вставленный узел абзаца. Это тот же узел, что и[`CurrentParagraph`](../currentparagraph/).

### Примечания

Текущее форматирование абзаца, заданное параметром[`ParagraphFormat`](../paragraphformat/) используется свойство.

Разбивает текущий абзац на два. После вставки абзаца курсор помещается в начало нового абзаца.

### Примеры

Показывает, как вставить абзац в документ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;
paragraphFormat.KeepTogether = true;

// Метод Writeln завершает абзац после добавления текста
// и затем начинает новую строку, добавляя новый абзац.
builder.Writeln("Hello world!");

Assert.True(builder.CurrentParagraph.IsEndOfDocument);
```

### Смотрите также

* class [Paragraph](../../paragraph/)
* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


