---
title: IFieldMergingCallback.FieldMerging
second_title: Aspose.Words für .NET-API-Referenz
description: IFieldMergingCallback methode. Wird aufgerufen wenn die SerienbriefEngine von Aspose.Words Daten in ein Briefvorlagenfeld im Dokument einfügen will.
type: docs
weight: 10
url: /de/net/aspose.words.mailmerging/ifieldmergingcallback/fieldmerging/
---
## IFieldMergingCallback.FieldMerging method

Wird aufgerufen, wenn die Serienbrief-Engine von Aspose.Words Daten in ein Briefvorlagenfeld im Dokument einfügen will.

```csharp
public void FieldMerging(FieldMergingArgs args)
```

### Beispiele

Zeigt, wie in einem Datenbank-BLOB-Feld gespeicherte Bilder in einen Bericht eingefügt werden.

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

        // Öffnen Sie den Datenleser, der sich in einem Modus befinden muss, der alle Datensätze auf einmal liest.
        OleDbCommand cmd = new OleDbCommand(query, conn);
        IDataReader dataReader = cmd.ExecuteReader();

        doc.MailMerge.ExecuteWithRegions(dataReader, "Employees");
    }

    doc.Save(ArtifactsDir + "MailMergeEvent.ImageFromBlob.docx");

private class HandleMergeImageFieldFromBlob : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        // Nichts tun.
    }

    /// <summary>
    /// Dies wird aufgerufen, wenn ein Seriendruck auf ein MERGEFIELD im Dokument mit einem "Image:"-Tag im Namen trifft.
    /// </summary>
    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        MemoryStream imageStream = new MemoryStream((byte[])e.FieldValue);
        e.ImageStream = imageStream;
    }
}
```

Zeigt, wie Sie einen Seriendruck mit einem benutzerdefinierten Rückruf ausführen, der Zusammenführungsdaten in Form von HTML-Dokumenten verarbeitet.

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
/// Wenn der Seriendruck auf ein MERGEFIELD trifft, dessen Name mit dem Präfix "html_" beginnt,
/// Dieser Callback parst seine Zusammenführungsdaten als HTML-Inhalt und fügt das Ergebnis dem Dokumentspeicherort von MERGEFIELD hinzu.
/// </summary>
private class HandleMergeFieldInsertHtml : IFieldMergingCallback
{
    /// <summary>
    /// Wird aufgerufen, wenn bei einem Seriendruck Daten in einem MERGEFIELD zusammengeführt werden.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName.StartsWith("html_") && args.Field.GetFieldCode().Contains("\\b"))
        {
            // Geparste HTML-Daten zum Hauptteil des Dokuments hinzufügen.
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);
            builder.InsertHtml((string)args.FieldValue);

            // Da wir den zusammengeführten Inhalt bereits manuell eingefügt haben,
             // Wir müssen auf dieses Ereignis nicht reagieren, indem wir Inhalte über die Eigenschaft "Text" zurückgeben.
            args.Text = string.Empty;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // Nichts tun.
    }
}
```

### Siehe auch

* class [FieldMergingArgs](../../fieldmergingargs/)
* interface [IFieldMergingCallback](../)
* namensraum [Aspose.Words.MailMerging](../../ifieldmergingcallback/)
* Montage [Aspose.Words](../../../)


