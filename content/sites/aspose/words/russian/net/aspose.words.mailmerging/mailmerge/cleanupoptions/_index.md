---
title: MailMerge.CleanupOptions
second_title: Справочник по API Aspose.Words для .NET
description: MailMerge свойство. Получает или задает набор флагов указывающих какие элементы должны быть удалены во время слияния.
type: docs
weight: 10
url: /ru/net/aspose.words.mailmerging/mailmerge/cleanupoptions/
---
## MailMerge.CleanupOptions property

Получает или задает набор флагов, указывающих, какие элементы должны быть удалены во время слияния.

```csharp
public MailMergeCleanupOptions CleanupOptions { get; set; }
```

### Примеры

Показывает, как удалить пустые абзацы, которые может создать слияние, из выходного документа слияния.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD TableStart:MyTable");
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertField(" MERGEFIELD TableEnd:MyTable");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "", "" });
dataTable.Rows.Add(new object[] { "Jane", "Doe" });

doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.ExecuteWithRegions(dataTable);

if (doc.MailMerge.CleanupOptions == MailMergeCleanupOptions.RemoveEmptyParagraphs) 
    Assert.AreEqual(
        "John Doe\r" +
        "Jane Doe", doc.GetText().Trim());
else
    Assert.AreEqual(
        "John Doe\r" +
        " \r" +
        "Jane Doe", doc.GetText().Trim());
```

Показывает, как автоматически удалять поля MERGEFIELD, которые не используются во время слияния почты.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте документ с MERGEFIELD для трех столбцов таблицы источника данных слияния,
// а затем создайте таблицу только с двумя столбцами, имена которых соответствуют нашим полям MERGEFIELD.
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "Joe", "Bloggs" });

// Наше третье поле MERGEFIELD ссылается на столбец «Город», которого нет в нашем источнике данных.
// Слияние почты оставит такие поля нетронутыми в их состоянии перед слиянием.
// Установка для свойства "CleanupOptions" значения "RemoveUnusedFields" удалит все поля MERGEFIELD
// которые не используются во время слияния для очистки документов слияния.
doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.Execute(dataTable);

if (mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveUnusedFields || 
    mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveStaticFields)
    Assert.AreEqual(0, doc.Range.Fields.Count);
else
    Assert.AreEqual(2, doc.Range.Fields.Count);
```

### Смотрите также

* enum [MailMergeCleanupOptions](../../mailmergecleanupoptions/)
* class [MailMerge](../)
* пространство имен [Aspose.Words.MailMerging](../../mailmerge/)
* сборка [Aspose.Words](../../../)


