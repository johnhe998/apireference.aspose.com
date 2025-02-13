---
title: FieldIndex.PageRangeSeparator
second_title: Справочник по API Aspose.Words для .NET
description: FieldIndex свойство. Получает или задает последовательность символов используемую для разделения начала и конца диапазона страниц.
type: docs
weight: 130
url: /ru/net/aspose.words.fields/fieldindex/pagerangeseparator/
---
## FieldIndex.PageRangeSeparator property

Получает или задает последовательность символов, используемую для разделения начала и конца диапазона страниц.

```csharp
public string PageRangeSeparator { get; set; }
```

### Примеры

Показывает, как указать составные страницы закладки в качестве диапазона страниц для записи в поле ИНДЕКС.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создать поле INDEX, которое будет отображать запись для каждого поля XE, найденного в документе.
// Каждая запись будет отображать значение свойства Text поля XE с левой стороны,
// и номер страницы, содержащей поле XE справа.
// Запись INDEX соберет все поля XE с совпадающими значениями в свойстве "Текст"
// в одну запись вместо создания записи для каждого поля XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Для записей INDEX, которые отображают диапазоны страниц, мы можем указать строку-разделитель
// который появится между номером первой страницы и номером последней.
index.PageNumberSeparator = ", on page(s) ";
index.PageRangeSeparator = " to ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\g \" to \"", index.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "My entry";

// Если поле XE называет закладку с помощью свойства PageRangeBookmarkName,
// его запись INDEX покажет диапазон страниц, которые охватывает закладка
// вместо номера страницы, содержащей поле XE.
indexEntry.PageRangeBookmarkName = "MyBookmark";

Assert.AreEqual(" XE  \"My entry\" \\r MyBookmark", indexEntry.GetFieldCode());
Assert.AreEqual("MyBookmark", indexEntry.PageRangeBookmarkName);

// Вставить закладку, которая начинается на странице 3 и заканчивается на странице 5.
// Запись INDEX для поля XE, которое ссылается на эту закладку, будет отображать этот диапазон страниц.
// В нашей таблице запись ИНДЕКС будет отображать "Моя запись, на страницах с 3 по 5".
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MyBookmark");
builder.Write("Start of MyBookmark");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.Write("End of MyBookmark");
builder.EndBookmark("MyBookmark");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageRangeBookmark.docx");
```

### Смотрите также

* class [FieldIndex](../)
* пространство имен [Aspose.Words.Fields](../../fieldindex/)
* сборка [Aspose.Words](../../../)


