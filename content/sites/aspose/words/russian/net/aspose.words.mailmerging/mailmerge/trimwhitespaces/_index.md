---
title: MailMerge.TrimWhitespaces
second_title: Справочник по API Aspose.Words для .NET
description: MailMerge свойство. Получает или задает значение указывающее обрезаются ли конечные и начальные пробелы из значений слияния.
type: docs
weight: 130
url: /ru/net/aspose.words.mailmerging/mailmerge/trimwhitespaces/
---
## MailMerge.TrimWhitespaces property

Получает или задает значение, указывающее, обрезаются ли конечные и начальные пробелы из значений слияния.

```csharp
public bool TrimWhitespaces { get; set; }
```

### Примечания

Значение по умолчанию: **истинный** .

### Примеры

Показывает, как обрезать пробелы в значениях источника данных при выполнении слияния.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD myMergeField", null);

doc.MailMerge.TrimWhitespaces = trimWhitespaces;
doc.MailMerge.Execute(new[] { "myMergeField" }, new object[] { "\t hello world! " });

Assert.AreEqual(trimWhitespaces ? "hello world!\f" : "\t hello world! \f", doc.GetText());
```

### Смотрите также

* class [MailMerge](../)
* пространство имен [Aspose.Words.MailMerging](../../mailmerge/)
* сборка [Aspose.Words](../../../)


