---
title: StructuredDocumentTag.Level
second_title: Справочник по API Aspose.Words для .NET
description: StructuredDocumentTag свойство. Получает уровень на котором СДТ встречается в дереве документа.
type: docs
weight: 170
url: /ru/net/aspose.words.markup/structureddocumenttag/level/
---
## StructuredDocumentTag.Level property

Получает уровень, на котором **СДТ** встречается в дереве документа.

```csharp
public MarkupLevel Level { get; }
```

### Примеры

Показывает, как создать тег структурированного документа в обычном текстовом поле и изменить его внешний вид.

```csharp
Document doc = new Document();

// Создайте тег структурированного документа, который будет содержать обычный текст.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Установите заголовок и цвет рамки, которая появляется при наведении указателя мыши на тег структурированного документа в Microsoft Word.
tag.Title = "My plain text";
tag.Color = Color.Magenta;

// Установить тег для этого тега структурированного документа, который можно получить
// как XML-элемент с именем "tag", со строкой ниже в его атрибуте "@val".
tag.Tag = "MyPlainTextSDT";

// Каждый тег структурированного документа имеет случайный уникальный идентификатор.
Assert.That(tag.Id, Is.Positive);

// Установите шрифт для текста внутри тега структурированного документа.
tag.ContentsFont.Name = "Arial";

// Установите шрифт для текста в конце тега структурированного документа.
// Любой текст, который мы набираем в теле документа после выхода из тега с помощью клавиш со стрелками, будет использовать этот шрифт.
tag.EndCharacterFont.Name = "Arial Black";

// По умолчанию это false, и нажатие клавиши ввода внутри тега структурированного документа ничего не делает.
// Если установлено значение true, наш тег структурированного документа может состоять из нескольких строк.

// Установите для свойства "Multiline" значение "false", чтобы разрешить только содержимое
// этого тега структурированного документа, чтобы занимать одну строку.
// Установите для свойства «Multiline» значение «true», чтобы тег мог содержать несколько строк содержимого.
tag.Multiline = true;

// Установите для свойства «Внешний вид» значение «SdtAppearance.Tags», чтобы отображать теги вокруг контента.
 // По умолчанию тег структурированного документа отображается как BoundingBox.
tag.Appearance = SdtAppearance.Tags;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(tag);

// Вставьте клон тега нашего структурированного документа в новый абзац.
StructuredDocumentTag tagClone = (StructuredDocumentTag)tag.Clone(true);
builder.InsertParagraph();
builder.InsertNode(tagClone);

// Используйте метод "RemoveSelfOnly", чтобы удалить тег структурированного документа, сохраняя при этом его содержимое в документе.
tagClone.RemoveSelfOnly();

doc.Save(ArtifactsDir + "StructuredDocumentTag.PlainText.docx");
```

### Смотрите также

* enum [MarkupLevel](../../markuplevel/)
* class [StructuredDocumentTag](../)
* пространство имен [Aspose.Words.Markup](../../structureddocumenttag/)
* сборка [Aspose.Words](../../../)


