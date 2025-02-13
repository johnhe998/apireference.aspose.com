---
title: FieldIndex.LetterRange
second_title: Справочник по API Aspose.Words для .NET
description: FieldIndex свойство. Получает или задает диапазон букв которым ограничивается индекс.
type: docs
weight: 90
url: /ru/net/aspose.words.fields/fieldindex/letterrange/
---
## FieldIndex.LetterRange property

Получает или задает диапазон букв, которым ограничивается индекс.

```csharp
public string LetterRange { get; set; }
```

### Примеры

Показывает, как заполнить поле INDEX записями, используя поля XE, а также изменить его внешний вид.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создать поле INDEX, которое будет отображать запись для каждого поля XE, найденного в документе.
// Каждая запись будет отображать значение свойства Text поля XE с левой стороны,
// и номер страницы, содержащей поле XE справа.
// Если поля XE имеют одинаковое значение в свойстве «Текст»,
// поле ИНДЕКС сгруппирует их в одну запись.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);
index.LanguageId = "1033";

// Установка значения этого свойства в "A" сгруппирует все записи по их первой букве,
// и поместите эту букву в верхнем регистре над каждой группой.
index.Heading = "A";

// Устанавливаем таблицу, созданную полем INDEX, на 2 столбца.
index.NumberOfColumns = "2";

// Установить, что любые записи с начальными буквами за пределами диапазона символов "ac" должны быть опущены.
index.LetterRange = "a-c";

Assert.AreEqual(" INDEX  \\z 1033 \\h A \\c 2 \\p a-c", index.GetFieldCode());

// Следующие два поля XE будут отображаться под заголовком «A»,
// с их соответствующими стилями текста, которые также применяются к их номерам страниц.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apple";
indexEntry.IsItalic = true;

Assert.AreEqual(" XE  Apple \\i", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apricot";
indexEntry.IsBold = true;

Assert.AreEqual(" XE  Apricot \\b", indexEntry.GetFieldCode());

// Оба следующих двух поля XE будут под заголовками "B" и "C" в таблице содержания полей INDEX.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Banana";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cherry";

// Поля ИНДЕКС сортируют все записи в алфавитном порядке, поэтому эта запись будет отображаться под буквой «А» вместе с двумя другими.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Avocado";

// Эта запись не появится, потому что она начинается с буквы "D",
// который находится за пределами диапазона символов "ac", определяемого свойством LetterRange поля INDEX.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Durian";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Formatting.docx");
```

### Смотрите также

* class [FieldIndex](../)
* пространство имен [Aspose.Words.Fields](../../fieldindex/)
* сборка [Aspose.Words](../../../)


