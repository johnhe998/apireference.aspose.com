---
title: Class StyleCollection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.StyleCollection сорт. Коллекция объектов Style представляющих как встроенные так и определяемые пользователем стили в документе.
type: docs
weight: 5840
url: /ru/net/aspose.words/stylecollection/
---
## StyleCollection class

Коллекция объектов Style, представляющих как встроенные, так и определяемые пользователем стили в документе.

```csharp
public class StyleCollection : IEnumerable<Style>
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words/stylecollection/count/) { get; } | Получает количество стилей в коллекции. |
| [DefaultFont](../../aspose.words/stylecollection/defaultfont/) { get; } | Получает форматирование текста документа по умолчанию. |
| [DefaultParagraphFormat](../../aspose.words/stylecollection/defaultparagraphformat/) { get; } | Получает форматирование абзаца документа по умолчанию. |
| [Document](../../aspose.words/stylecollection/document/) { get; } | Получает документ владельца. |
| [Item](../../aspose.words/stylecollection/item/) { get; } | Получает стиль по имени или псевдониму. (3 indexers) |

## Методы

| Имя | Описание |
| --- | --- |
| [Add](../../aspose.words/stylecollection/add/)(StyleType, string) | Создает новый пользовательский стиль и добавляет его в коллекцию. |
| [AddCopy](../../aspose.words/stylecollection/addcopy/)(Style) | Копирует стиль в эту коллекцию. |
| [ClearQuickStyleGallery](../../aspose.words/stylecollection/clearquickstylegallery/)() | Удаляет все стили из панели галереи быстрых стилей. |
| [GetEnumerator](../../aspose.words/stylecollection/getenumerator/)() | Получает объект перечислителя, который будет перечислять стили в алфавитном порядке их имен. |

### Примеры

Показывает, как создать и использовать стиль абзаца с форматированием списка.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создать собственный стиль абзаца.
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// Создайте список и убедитесь, что абзацы, использующие этот стиль, будут использовать этот список.
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// Применяем стиль абзаца к текущему абзацу конструктора документов, а затем добавляем текст.
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// Измените стиль построителя документа на стиль без форматирования списка и напишите еще один абзац.
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### Смотрите также

* class [Style](../style/)
* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


