---
title: FootnoteOptions.Position
second_title: Справочник по API Aspose.Words для .NET
description: FootnoteOptions свойство. Определяет положение сносок.
type: docs
weight: 30
url: /ru/net/aspose.words.notes/footnoteoptions/position/
---
## FootnoteOptions.Position property

Определяет положение сносок.

```csharp
public FootnotePosition Position { get; set; }
```

### Примеры

Показывает, как выбрать другое место, где документ будет собирать и отображать свои сноски.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Сноска — это способ прикрепить ссылку или комментарий к тексту
// это не мешает потоку основного текста.  
// Вставка сноски добавляет небольшой верхний индекс ссылки
// в основном тексте, где мы вставляем сноску.
// Каждая сноска также создает запись внизу страницы, состоящую из символа
// который соответствует ссылочному символу в основном тексте.
// Ссылочный текст, который мы передаем методу "InsertFootnote" построителя документа.
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote contents.");

// Мы можем использовать свойство «Позиция», чтобы определить, где документ будет размещать все свои сноски.
// Если мы установим значение свойства "Position" в "FootnotePosition.BottomOfPage",
// каждая сноска будет отображаться внизу страницы, содержащей соответствующую метку. Это значение по умолчанию.
// Если мы установим значение свойства "Позиция" в "FootnotePosition.BeneathText",
// каждая сноска будет отображаться в конце текста страницы, содержащего ее контрольную отметку.
doc.FootnoteOptions.Position = footnotePosition;

doc.Save(ArtifactsDir + "InlineStory.PositionFootnote.docx");
```

### Смотрите также

* enum [FootnotePosition](../../footnoteposition/)
* class [FootnoteOptions](../)
* пространство имен [Aspose.Words.Notes](../../footnoteoptions/)
* сборка [Aspose.Words](../../../)


