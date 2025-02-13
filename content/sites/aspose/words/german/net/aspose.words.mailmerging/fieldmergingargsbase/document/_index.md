---
title: FieldMergingArgsBase.Document
second_title: Aspose.Words für .NET-API-Referenz
description: FieldMergingArgsBase eigendom. Gibt die zurückDocument Objekt für das der Seriendruck durchgeführt wird.
type: docs
weight: 10
url: /de/net/aspose.words.mailmerging/fieldmergingargsbase/document/
---
## FieldMergingArgsBase.Document property

Gibt die zurück`Document` Objekt, für das der Seriendruck durchgeführt wird.

```csharp
public Document Document { get; }
```

### Beispiele

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

* class [Document](../../../aspose.words/document/)
* class [FieldMergingArgsBase](../)
* namensraum [Aspose.Words.MailMerging](../../fieldmergingargsbase/)
* Montage [Aspose.Words](../../../)


