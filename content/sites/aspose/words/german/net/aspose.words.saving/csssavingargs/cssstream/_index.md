---
title: CssSavingArgs.CssStream
second_title: Aspose.Words für .NET-API-Referenz
description: CssSavingArgs eigendom. Ermöglicht die Angabe des Streams in dem die CSSInformationen gespeichert werden.
type: docs
weight: 10
url: /de/net/aspose.words.saving/csssavingargs/cssstream/
---
## CssSavingArgs.CssStream property

Ermöglicht die Angabe des Streams, in dem die CSS-Informationen gespeichert werden.

```csharp
public Stream CssStream { get; set; }
```

### Bemerkungen

Mit dieser Eigenschaft können Sie CSS-Informationen in einem Stream speichern.

Der Standardwert ist`Null` Diese Eigenschaft unterdrückt nicht das Speichern von CSS-Informationen in einer Datei oder das Einbetten in ein HTML-Dokument. Um den Export von CSS zu unterdrücken, verwenden Sie die[`IsExportNeeded`](../isexportneeded/) Eigentum.

Verwenden[`ICssSavingCallback`](../../icsssavingcallback/) Sie können CSS nicht durch ersetzen. Es ist nur zum Speichern von CSS in einem Stream vorgesehen.

### Beispiele

Zeigt, wie Sie mit CSS-Stylesheets arbeiten, die eine HTML-Konvertierung erstellt.

```csharp
public void ExternalCssFilenames()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Erstellen Sie ein "HtmlFixedSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
    // um zu ändern, wie wir das Dokument in HTML konvertieren.
    HtmlSaveOptions options = new HtmlSaveOptions();

    // Legen Sie die Eigenschaft "CssStylesheetType" auf "CssStyleSheetType.External" fest
    // ein gespeichertes HTML-Dokument mit einer externen CSS-Stylesheet-Datei begleiten.
    options.CssStyleSheetType = CssStyleSheetType.External;

    // Im Folgenden finden Sie zwei Möglichkeiten, Verzeichnisse und Dateinamen für Ausgabe-CSS-Stylesheets anzugeben.
    // 1 - Verwenden Sie die Eigenschaft "CssStyleSheetFileName", um unserem Stylesheet einen Dateinamen zuzuweisen:
    options.CssStyleSheetFileName = ArtifactsDir + "SavingCallback.ExternalCssFilenames.css";

    // 2 - Verwenden Sie einen benutzerdefinierten Callback, um unser Stylesheet zu benennen:
    options.CssSavingCallback =
        new CustomCssSavingCallback(ArtifactsDir + "SavingCallback.ExternalCssFilenames.css", true, false);

    doc.Save(ArtifactsDir + "SavingCallback.ExternalCssFilenames.html", options);
}

/// <summary>
/// Legt einen benutzerdefinierten Dateinamen zusammen mit anderen Parametern für ein externes CSS-Stylesheet fest.
/// </summary>
private class CustomCssSavingCallback : ICssSavingCallback
{
    public CustomCssSavingCallback(string cssDocFilename, bool isExportNeeded, bool keepCssStreamOpen)
    {
        mCssTextFileName = cssDocFilename;
        mIsExportNeeded = isExportNeeded;
        mKeepCssStreamOpen = keepCssStreamOpen;
    }

    public void CssSaving(CssSavingArgs args)
    {
        // Über die Eigenschaft "Document" können wir auf das gesamte Quelldokument zugreifen.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        args.CssStream = new FileStream(mCssTextFileName, FileMode.Create);
        args.IsExportNeeded = mIsExportNeeded;
        args.KeepCssStreamOpen = mKeepCssStreamOpen;

        Assert.True(args.CssStream.CanWrite);
    }

    private readonly string mCssTextFileName;
    private readonly bool mIsExportNeeded;
    private readonly bool mKeepCssStreamOpen;
}
```

### Siehe auch

* class [CssSavingArgs](../)
* namensraum [Aspose.Words.Saving](../../csssavingargs/)
* Montage [Aspose.Words](../../../)


