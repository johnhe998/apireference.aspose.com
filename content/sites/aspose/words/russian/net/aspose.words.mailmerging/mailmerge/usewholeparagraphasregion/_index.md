---
title: MailMerge.UseWholeParagraphAsRegion
second_title: Справочник по API Aspose.Words для .NET
description: MailMerge свойство. Получает или задает значение указывающее следует ли включать в область слияния весь абзац с полем TableStart или TableEnd или определенный диапазон между полями TableStart и TableEnd.
type: docs
weight: 160
url: /ru/net/aspose.words.mailmerging/mailmerge/usewholeparagraphasregion/
---
## MailMerge.UseWholeParagraphAsRegion property

Получает или задает значение, указывающее, следует ли включать в область слияния весь абзац с полем TableStart или TableEnd или определенный диапазон между полями TableStart и TableEnd.

```csharp
public bool UseWholeParagraphAsRegion { get; set; }
```

### Примечания

Значение по умолчанию: **истинный** .

### Примеры

Показывает взаимосвязь между областями слияния и абзацами.

```csharp
public void UseWholeParagraphAsRegion(bool useWholeParagraphAsRegion)
{
    Document doc = CreateSourceDocWithNestedMergeRegions();
    DataTable dataTable = CreateSourceTableDataTableForOneRegion();

    // По умолчанию абзац может принадлежать не более чем к одному региону слияния.
    // Содержимое нашего документа не соответствует этим критериям.
    // Если мы установим флаг "UseWholeParagraphAsRegion" в "true",
    // выполнение слияния для этого документа вызовет исключение.
    // Если мы установим флаг "UseWholeParagraphAsRegion" в "false",
    // мы сможем выполнить слияние с этим документом.
    doc.MailMerge.UseWholeParagraphAsRegion = useWholeParagraphAsRegion;

    if (useWholeParagraphAsRegion)
        Assert.Throws<InvalidOperationException>(() => doc.MailMerge.ExecuteWithRegions(dataTable));
    else
        doc.MailMerge.ExecuteWithRegions(dataTable);

    // Слияние почты заполняет наш первый регион, оставляя второй регион неиспользованным
    // так как это регион, который нарушает правило.
    doc.Save(ArtifactsDir + "MailMerge.UseWholeParagraphAsRegion.docx");
}

/// <summary>
/// Создайте документ с двумя областями слияния, разделяющими один абзац.
/// </summary>
private static Document CreateSourceDocWithNestedMergeRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Write("Region 1: ");
    builder.InsertField(" MERGEFIELD TableStart:MyTable");
    builder.InsertField(" MERGEFIELD Column1");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Column2");
    builder.InsertField(" MERGEFIELD TableEnd:MyTable");

    builder.Write(", Region 2: ");
    builder.InsertField(" MERGEFIELD TableStart:MyOtherTable");
    builder.InsertField(" MERGEFIELD TableEnd:MyOtherTable");

    return doc;
}

/// <summary>
/// Создать таблицу данных, которая может заполнить один регион во время слияния.
/// </summary>
private static DataTable CreateSourceTableDataTableForOneRegion()
{
    DataTable dataTable = new DataTable("MyTable");
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


