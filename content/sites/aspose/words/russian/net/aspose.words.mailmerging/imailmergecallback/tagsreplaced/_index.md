---
title: IMailMergeCallback.TagsReplaced
second_title: Справочник по API Aspose.Words для .NET
description: IMailMergeCallback метод. Вызывается когда текстовые теги усы заменяются полями MERGEFIELD.
type: docs
weight: 10
url: /ru/net/aspose.words.mailmerging/imailmergecallback/tagsreplaced/
---
## IMailMergeCallback.TagsReplaced method

Вызывается, когда текстовые теги "усы" заменяются полями MERGEFIELD.

```csharp
public void TagsReplaced()
```

### Примеры

Показывает, как определить пользовательскую логику для обработки событий во время слияния.

```csharp
public void Callback()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Вставьте два тега слияния, ссылающихся на два столбца в источнике данных.
    builder.Write("{{FirstName}}");
    builder.Write("{{LastName}}");

    // Создайте источник данных, который содержит только один из столбцов, на которые ссылаются наши теги слияния.
    DataTable table = new DataTable("Test");
    table.Columns.Add("FirstName");
    table.Rows.Add("John");
    table.Rows.Add("Jane");

    // Настройте наше слияние для использования альтернативных тегов слияния.
    doc.MailMerge.UseNonMergeFields = true;

    // Затем убедитесь, что слияние конвертирует теги, такие как наш тег "LastName",
    // в поля MERGEFIELD в документах слияния.
    doc.MailMerge.PreserveUnusedTags = false;

    MailMergeTagReplacementCounter counter = new MailMergeTagReplacementCounter();
    doc.MailMerge.MailMergeCallback = counter;
    doc.MailMerge.Execute(table);

    Assert.AreEqual(1, counter.TagsReplacedCount);
}

/// <summary>
/// Подсчитывает количество раз, когда слияние заменяет теги слияния, которые не могут быть заполнены данными с помощью полей MERGEFIELD.
/// </summary>
private class MailMergeTagReplacementCounter : IMailMergeCallback
{
    public void TagsReplaced()
    {
        TagsReplacedCount++;
    }

    public int TagsReplacedCount { get; private set; }
}
```

### Смотрите также

* property [UseNonMergeFields](../../mailmerge/usenonmergefields/)
* interface [IMailMergeCallback](../)
* пространство имен [Aspose.Words.MailMerging](../../imailmergecallback/)
* сборка [Aspose.Words](../../../)


