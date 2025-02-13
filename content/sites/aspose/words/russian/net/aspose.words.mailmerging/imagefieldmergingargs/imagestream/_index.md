---
title: ImageFieldMergingArgs.ImageStream
second_title: Справочник по API Aspose.Words для .NET
description: ImageFieldMergingArgs свойство. Указывает поток из которого механизм слияния считывает изображение.
type: docs
weight: 40
url: /ru/net/aspose.words.mailmerging/imagefieldmergingargs/imagestream/
---
## ImageFieldMergingArgs.ImageStream property

Указывает поток, из которого механизм слияния считывает изображение.

```csharp
public Stream ImageStream { get; set; }
```

### Примечания

Aspose.Words закрывает этот поток после слияния изображения с документом.

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

### Смотрите также

* class [ImageFieldMergingArgs](../)
* пространство имен [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* сборка [Aspose.Words](../../../)


