---
title: Class FieldMergingArgsBase
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.MailMerging.FieldMergingArgsBase klas. Basisklasse fürFieldMergingArgs undImageFieldMergingArgs .
type: docs
weight: 3560
url: /de/net/aspose.words.mailmerging/fieldmergingargsbase/
---
## FieldMergingArgsBase class

Basisklasse für[`FieldMergingArgs`](../fieldmergingargs/) und[`ImageFieldMergingArgs`](../imagefieldmergingargs/) .

```csharp
public abstract class FieldMergingArgsBase
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Document](../../aspose.words.mailmerging/fieldmergingargsbase/document/) { get; } | Gibt die zurück[`Document`](./document/) Objekt, für das der Seriendruck durchgeführt wird. |
| [DocumentFieldName](../../aspose.words.mailmerging/fieldmergingargsbase/documentfieldname/) { get; } | Ruft den Namen des Briefvorlagenfelds ab, wie im Dokument angegeben. |
| [Field](../../aspose.words.mailmerging/fieldmergingargsbase/field/) { get; } | Ruft das Objekt ab, das das aktuelle Briefvorlagenfeld darstellt. |
| [FieldName](../../aspose.words.mailmerging/fieldmergingargsbase/fieldname/) { get; } | Ruft den Namen des Briefvorlagenfelds in der Datenquelle ab. |
| [FieldValue](../../aspose.words.mailmerging/fieldmergingargsbase/fieldvalue/) { get; set; } | Ruft den Wert des Felds aus der Datenquelle ab oder legt ihn fest. |
| [RecordIndex](../../aspose.words.mailmerging/fieldmergingargsbase/recordindex/) { get; } | Ruft den nullbasierten Index des Datensatzes ab, der zusammengeführt wird. |
| [TableName](../../aspose.words.mailmerging/fieldmergingargsbase/tablename/) { get; } | Ruft den Namen der Datentabelle für den aktuellen Zusammenführungsvorgang oder eine leere Zeichenfolge ab, wenn der Name nicht verfügbar ist. |

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

* namensraum [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* Montage [Aspose.Words](../../)


