---
title: MailMerge.FieldMergingCallback
second_title: Aspose.Words för .NET API Referens
description: MailMerge fast egendom. Förekommer under sammankoppling när ett sammanslagningsfält påträffas i dokumentet.
type: docs
weight: 30
url: /sv/net/aspose.words.mailmerging/mailmerge/fieldmergingcallback/
---
## MailMerge.FieldMergingCallback property

Förekommer under sammankoppling när ett sammanslagningsfält påträffas i dokumentet.

```csharp
public IFieldMergingCallback FieldMergingCallback { get; set; }
```

### Exempel

Visar hur man infogar bilder lagrade i ett databas BLOB-fält i en rapport.

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

        // Öppna dataläsaren, som måste vara i ett läge som läser alla poster samtidigt.
        OleDbCommand cmd = new OleDbCommand(query, conn);
        IDataReader dataReader = cmd.ExecuteReader();

        doc.MailMerge.ExecuteWithRegions(dataReader, "Employees");
    }

    doc.Save(ArtifactsDir + "MailMergeEvent.ImageFromBlob.docx");

private class HandleMergeImageFieldFromBlob : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        // Göra ingenting.
    }

    /// <summary>
    /// Detta kallas när en sammanslagning stöter på ett MERGEFIELD i dokumentet med en "Image:"-tagg i sitt namn.
    /// </summary>
    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        MemoryStream imageStream = new MemoryStream((byte[])e.FieldValue);
        e.ImageStream = imageStream;
    }
}
```

Visar hur man utför en sammankoppling med en anpassad återuppringning som hanterar sammanslagningsdata i form av HTML-dokument.

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
/// Om kopplingen stöter på ett MERGEFIELD vars namn börjar med prefixet "html_",
/// denna återuppringning analyserar dess sammanslagningsdata som HTML-innehåll och lägger till resultatet till dokumentplatsen för MERGEFIELD.
/// </summary>
private class HandleMergeFieldInsertHtml : IFieldMergingCallback
{
    /// <summary>
    /// Anropas när en e-postsammanfogning slår samman data till ett MERGEFIELD.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName.StartsWith("html_") && args.Field.GetFieldCode().Contains("\\b"))
        {
            // Lägg till analyserad HTML-data till dokumentets brödtext.
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);
            builder.InsertHtml((string)args.FieldValue);

            // Eftersom vi redan har infogat det sammanslagna innehållet manuellt,
              // vi behöver inte svara på denna händelse genom att returnera innehåll via "Text"-egenskapen.
            args.Text = string.Empty;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // Göra ingenting.
    }
}
```

### Se även

* interface [IFieldMergingCallback](../../ifieldmergingcallback/)
* class [MailMerge](../)
* namnutrymme [Aspose.Words.MailMerging](../../mailmerge/)
* hopsättning [Aspose.Words](../../../)


