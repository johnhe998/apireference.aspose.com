---
title: MailMerge.MergeDuplicateRegions
second_title: Справочник по API Aspose.Words для .NET
description: MailMerge свойство. Получает или задает значение указывающее следует ли объединять все области слияния документов с именем источника данных при выполнении слияния с областями для источника данных или только первую.
type: docs
weight: 60
url: /ru/net/aspose.words.mailmerging/mailmerge/mergeduplicateregions/
---
## MailMerge.MergeDuplicateRegions property

Получает или задает значение, указывающее, следует ли объединять все области слияния документов с именем источника данных при выполнении слияния с областями для источника данных или только первую.

```csharp
public bool MergeDuplicateRegions { get; set; }
```

### Примечания

Значение по умолчанию: **ЛОЖЬ** .

### Примеры

Показывает, как работать с повторяющимися областями слияния.

```csharp
public void MergeDuplicateRegions(bool mergeDuplicateRegions)
{
    Document doc = CreateSourceDocMergeDuplicateRegions();
    DataTable dataTable = CreateSourceTableMergeDuplicateRegions();

    // Если мы установим для свойства "MergeDuplicateRegions" значение "false", слияние затронет первый регион,
    // в то время как поля MERGEFIELD второго останутся в состоянии до слияния.
    // Чтобы объединить обе области таким образом,
    // нам пришлось бы дважды выполнить слияние для таблицы с тем же именем.
    // Если мы установим для свойства "MergeDuplicateRegions" значение "true", слияние затронет оба региона.
    doc.MailMerge.MergeDuplicateRegions = mergeDuplicateRegions;

    doc.MailMerge.ExecuteWithRegions(dataTable);
    doc.Save(ArtifactsDir + "MailMerge.MergeDuplicateRegions.docx");
}

/// <summary>
/// Возвращает документ, который содержит две повторяющиеся области слияния (имеющие одно и то же имя в тегах TableStart/End).
/// </summary>
private static Document CreateSourceDocMergeDuplicateRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD TableStart:MergeRegion");
    builder.InsertField(" MERGEFIELD Column1");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion");
    builder.InsertParagraph();

    builder.InsertField(" MERGEFIELD TableStart:MergeRegion");
    builder.InsertField(" MERGEFIELD Column2");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion");

    return doc;
}

/// <summary>
/// Создает таблицу данных с одной строкой и двумя столбцами.
/// </summary>
private static DataTable CreateSourceTableMergeDuplicateRegions()
{
    DataTable dataTable = new DataTable("MergeRegion");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value 1", "Value 2" });

    return dataTable;
}
```

### Смотрите также

* class [MailMerge](../)
* пространство имен [Aspose.Words.MailMerging](../../mailmerge/)
* сборка [Aspose.Words](../../../)


