---
title: Enum FootnoteNumberingRule
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Notes.FootnoteNumberingRule перечисление. Определяет когда перезапускается автоматическая нумерация сносок или концевых сносок.
type: docs
weight: 4030
url: /ru/net/aspose.words.notes/footnotenumberingrule/
---
## FootnoteNumberingRule enumeration

Определяет, когда перезапускается автоматическая нумерация сносок или концевых сносок.

```csharp
public enum FootnoteNumberingRule
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Continuous | `0` | Нумерация непрерывна по всему документу. |
| RestartSection | `1` | Нумерация перезапускается в каждом разделе. |
| RestartPage | `2` | Нумерация начинается заново на каждой странице. Действительно только для сносок. |
| Default | `0` | равноContinuous . |

### Примеры

Показывает, как перезапустить нумерацию сносок/концевых сносок в определенных местах документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Сноски и концевые сноски — это способ прикрепить ссылку или комментарий к тексту
// это не мешает потоку основного текста. 
// При вставке сноски/концевой сноски добавляется маленький символ надстрочной ссылки
// в основном тексте, где мы вставляем сноску/концевую сноску.
// Каждая сноска/концевая сноска также создает запись, состоящую из символа, соответствующего ссылке
// символ в основном тексте. Ссылочный текст, который мы передаем методу «InsertEndnote» конструктора документов.
// Записи сносок по умолчанию отображаются внизу каждой страницы, содержащей
// их ссылочные символы и концевые сноски отображаются в конце документа.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 4.");

builder.InsertBreak(BreakType.PageBreak);

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 4.");

// По умолчанию ссылочным символом для каждой сноски и концевой сноски является ее индекс
// среди всех сносок/концевых сносок документа. Каждый документ ведет отдельные счета
// для сносок и концевых сносок и никогда не перезапускает эти счетчики.
Assert.AreEqual(doc.FootnoteOptions.RestartRule, FootnoteNumberingRule.Default);
Assert.AreEqual(FootnoteNumberingRule.Default, FootnoteNumberingRule.Continuous);

// Мы можем использовать свойство "RestartRule", чтобы перезапустить документ
// сноска/концевая сноска считается на новой странице или в разделе.
doc.FootnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
doc.EndnoteOptions.RestartRule = FootnoteNumberingRule.RestartSection;

doc.Save(ArtifactsDir + "InlineStory.NumberingRule.docx");
```

### Смотрите также

* class [FootnoteOptions](../footnoteoptions/)
* class [EndnoteOptions](../endnoteoptions/)
* пространство имен [Aspose.Words.Notes](../../aspose.words.notes/)
* сборка [Aspose.Words](../../)


