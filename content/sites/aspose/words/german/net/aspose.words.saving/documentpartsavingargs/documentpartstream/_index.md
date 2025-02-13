---
title: DocumentPartSavingArgs.DocumentPartStream
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentPartSavingArgs eigendom. Ermöglicht die Angabe des Streams in dem der Dokumentteil gespeichert wird.
type: docs
weight: 30
url: /de/net/aspose.words.saving/documentpartsavingargs/documentpartstream/
---
## DocumentPartSavingArgs.DocumentPartStream property

Ermöglicht die Angabe des Streams, in dem der Dokumentteil gespeichert wird.

```csharp
public Stream DocumentPartStream { get; set; }
```

### Bemerkungen

Mit dieser Eigenschaft können Sie beim HTML-Export Dokumentteile in Streams statt in Dateien speichern.

Der Standardwert ist`Null` . Wenn diese Eigenschaft ist`Null` , wird der Dokumentteil in einer Datei gespeichert, die in der angegeben ist[`DocumentPartFileName`](../documentpartfilename/) Eigentum.

Beim Speichern in einen Stream im HTML-Format wird von angefordert[`Save`](../../../aspose.words/document/save/) oder[`Save`](../../../aspose.words/document/save/) und der erste Teil des Dokuments gespeichert werden soll, schlägt Aspose.Words hier den ursprünglich vom Aufrufer übergebenen Hauptausgabestrom vor.

Beim Speichern im EPUB-Format, das ein auf HTML basierendes Containerformat ist,`DocumentPartStream` kann nicht angegeben werden, da alle untergeordneten Teile in einem einzigen Ausgabepaket gekapselt werden.

### Beispiele

Zeigt, wie ein Dokument in Teile aufgeteilt und gespeichert wird.

```csharp
public void DocumentPartsFileNames()
{
    Document doc = new Document(MyDir + "Rendering.docx");
    string outFileName = "SavingCallback.DocumentPartsFileNames.html";

    // Erstellen Sie ein "HtmlFixedSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
    // um zu ändern, wie wir das Dokument in HTML konvertieren.
    HtmlSaveOptions options = new HtmlSaveOptions();

    // Wenn wir das Dokument normal speichern, gibt es eine HTML-Ausgabe
    // Dokument mit dem gesamten Inhalt des Quelldokuments.
    // Legen Sie die Eigenschaft „DocumentSplitCriteria“ auf „DocumentSplitCriteria.SectionBreak“ fest
    // Unser Dokument in mehreren HTML-Dateien speichern: eine für jeden Abschnitt.
    options.DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak;

    // Weisen Sie der Eigenschaft "DocumentPartSavingCallback" einen benutzerdefinierten Rückruf zu, um die Speicherlogik des Dokumentteils zu ändern.
    options.DocumentPartSavingCallback = new SavedDocumentPartRename(outFileName, options.DocumentSplitCriteria);

    // Wenn wir ein Dokument, das Bilder enthält, in HTML umwandeln, erhalten wir am Ende eine HTML-Datei, die auf mehrere Bilder verweist.
    // Jedes Bild liegt in Form einer Datei im lokalen Dateisystem vor.
    // Es gibt auch einen Rückruf, der den Namen und den Speicherort des Dateisystems jedes Bildes anpassen kann.
    options.ImageSavingCallback = new SavedImageRename(outFileName);

    doc.Save(ArtifactsDir + outFileName, options);
}

/// <summary>
/// Legt benutzerdefinierte Dateinamen für Ausgabedokumente fest, in die der Speichervorgang ein Dokument aufteilt.
/// </summary>
private class SavedDocumentPartRename : IDocumentPartSavingCallback
{
    public SavedDocumentPartRename(string outFileName, DocumentSplitCriteria documentSplitCriteria)
    {
        mOutFileName = outFileName;
        mDocumentSplitCriteria = documentSplitCriteria;
    }

    void IDocumentPartSavingCallback.DocumentPartSaving(DocumentPartSavingArgs args)
    {
        // Über die Eigenschaft "Document" können wir auf das gesamte Quelldokument zugreifen.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        string partType = string.Empty;

        switch (mDocumentSplitCriteria)
        {
            case DocumentSplitCriteria.PageBreak:
                partType = "Page";
                break;
            case DocumentSplitCriteria.ColumnBreak:
                partType = "Column";
                break;
            case DocumentSplitCriteria.SectionBreak:
                partType = "Section";
                break;
            case DocumentSplitCriteria.HeadingParagraph:
                partType = "Paragraph from heading";
                break;
        }

        string partFileName = $"{mOutFileName} part {++mCount}, of type {partType}{Path.GetExtension(args.DocumentPartFileName)}";

        // Im Folgenden finden Sie zwei Möglichkeiten, um anzugeben, wo Aspose.Words jeden Teil des Dokuments speichern wird.
        // 1 - Legen Sie einen Dateinamen für die Ausgabeteildatei fest:
        args.DocumentPartFileName = partFileName;

        // 2 - Erstellen Sie einen benutzerdefinierten Stream für die Ausgabeteildatei:
        args.DocumentPartStream = new FileStream(ArtifactsDir + partFileName, FileMode.Create);

        Assert.True(args.DocumentPartStream.CanWrite);
        Assert.False(args.KeepDocumentPartStreamOpen);
    }

    private int mCount;
    private readonly string mOutFileName;
    private readonly DocumentSplitCriteria mDocumentSplitCriteria;
}

/// <summary>
/// Legt benutzerdefinierte Dateinamen für Bilddateien fest, die eine HTML-Konvertierung erstellt.
/// </summary>
public class SavedImageRename : IImageSavingCallback
{
    public SavedImageRename(string outFileName)
    {
        mOutFileName = outFileName;
    }

    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        string imageFileName = $"{mOutFileName} shape {++mCount}, of type {args.CurrentShape.ShapeType}{Path.GetExtension(args.ImageFileName)}";

        // Im Folgenden finden Sie zwei Möglichkeiten, um anzugeben, wo Aspose.Words jeden Teil des Dokuments speichern wird.
        // 1 - Legen Sie einen Dateinamen für die Ausgabebilddatei fest:
        args.ImageFileName = imageFileName;

        // 2 - Erstellen Sie einen benutzerdefinierten Stream für die Ausgabebilddatei:
        args.ImageStream = new FileStream(ArtifactsDir + imageFileName, FileMode.Create);

        Assert.True(args.ImageStream.CanWrite);
        Assert.True(args.IsImageAvailable);
        Assert.False(args.KeepImageStreamOpen);
    }

    private int mCount;
    private readonly string mOutFileName;
}
```

### Siehe auch

* class [DocumentPartSavingArgs](../)
* namensraum [Aspose.Words.Saving](../../documentpartsavingargs/)
* Montage [Aspose.Words](../../../)


