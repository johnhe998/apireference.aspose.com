---
title: IFieldMergingCallback.FieldMerging
second_title: Справочник по API Aspose.Words для .NET
description: IFieldMergingCallback метод. Вызывается когда механизм слияния Aspose.Words собирается вставить данные в поле слияния в документе.
type: docs
weight: 10
url: /ru/net/aspose.words.mailmerging/ifieldmergingcallback/fieldmerging/
---
## IFieldMergingCallback.FieldMerging method

Вызывается, когда механизм слияния Aspose.Words собирается вставить данные в поле слияния в документе.

```csharp
public void FieldMerging(FieldMergingArgs args)
```

### Примеры

Показывает, как вставить изображения, хранящиеся в поле BLOB базы данных, в отчет.

```csharp
public void ImageFromBlob()
{
    Document doc = new Document(MyDir + "Mail merge destination - Northwind employees.docx");

    doc.MailMerge.FieldMergingCallback = new HandleMergeImageFieldFromBlob();

    string connString = $"Provider=Microsoft.Jet.OLEDB.4.0;Data Source={DatabaseDir + "Northwind.mdb"};";
    string query = "SELECT FirstName, LastName, Title, Address, City, Region, Country, PhotoBLOB FROM Employees";

    using (OleDbConnection conn = new OleDbConnection(connString))
    {
        conn.Open();

        // Откройте средство чтения данных, которое должно быть в режиме чтения всех записей одновременно.
        OleDbCommand cmd = new OleDbCommand(query, conn);
        IDataReader dataReader = cmd.ExecuteReader();

        doc.MailMerge.ExecuteWithRegions(dataReader, "Employees");
    }

    doc.Save(ArtifactsDir + "MailMergeEvent.ImageFromBlob.docx");

private class HandleMergeImageFieldFromBlob : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        // Ничего не делать.
    }

    /// <summary>
    /// Это вызывается, когда слияние встречает MERGEFIELD в документе с тегом «Image:» в его имени.
    /// </summary>
    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        MemoryStream imageStream = new MemoryStream((byte[])e.FieldValue);
        e.ImageStream = imageStream;
    }
}
```

Показывает, как выполнить слияние почты с помощью пользовательского обратного вызова, который обрабатывает данные слияния в виде HTML-документов.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(@"MERGEFIELD  html_Title  \b Content");
    builder.InsertField(@"MERGEFIELD  html_Body  \b Content");

    object[] mergeData =
    {
        "<html>" +
            "<h1>" +
                "<span style=\"color: #0000ff; font-family: Arial;\">Hello World!</span>" +
            "</h1>" +
        "</html>", 

        "<html>" +
            "<blockquote>" +
                "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>" +
            "</blockquote>" +
        "</html>"
    };

    doc.MailMerge.FieldMergingCallback = new HandleMergeFieldInsertHtml();
    doc.MailMerge.Execute(new[] { "html_Title", "html_Body" }, mergeData);

    doc.Save(ArtifactsDir + "MailMergeEvent.MergeHtml.docx");
}

/// <summary>
/// Если слияние почты встречает MERGEFIELD, имя которого начинается с префикса "html_",
/// этот обратный вызов анализирует свои данные слияния как содержимое HTML и добавляет результат в расположение документа MERGEFIELD.
/// </summary>
private class HandleMergeFieldInsertHtml : IFieldMergingCallback
{
    /// <summary>
    /// Вызывается, когда слияние почты объединяет данные в MERGEFIELD.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName.StartsWith("html_") && args.Field.GetFieldCode().Contains("\\b"))
        {
            // Добавляем проанализированные HTML-данные в тело документа.
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);
            builder.InsertHtml((string)args.FieldValue);

            // Так как мы уже вставили объединенный контент вручную,
             // нам не нужно будет реагировать на это событие, возвращая содержимое через свойство «Текст».
            args.Text = string.Empty;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // Ничего не делать.
    }
}
```

### Смотрите также

* class [FieldMergingArgs](../../fieldmergingargs/)
* interface [IFieldMergingCallback](../)
* пространство имен [Aspose.Words.MailMerging](../../ifieldmergingcallback/)
* сборка [Aspose.Words](../../../)


