---
title: FieldMergingArgsBase.Document
second_title: Aspose.Words för .NET API Referens
description: FieldMergingArgsBase fast egendom. ReturnerarDocument objekt för vilket sammanslagningen utförs.
type: docs
weight: 10
url: /sv/net/aspose.words.mailmerging/fieldmergingargsbase/document/
---
## FieldMergingArgsBase.Document property

Returnerar`Document` objekt för vilket sammanslagningen utförs.

```csharp
public Document Document { get; }
```

### Exempel

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

* class [Document](../../../aspose.words/document/)
* class [FieldMergingArgsBase](../)
* namnutrymme [Aspose.Words.MailMerging](../../fieldmergingargsbase/)
* hopsättning [Aspose.Words](../../../)


