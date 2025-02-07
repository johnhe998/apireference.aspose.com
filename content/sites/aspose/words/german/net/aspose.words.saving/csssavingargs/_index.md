---
title: Class CssSavingArgs
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.CssSavingArgs klas. Liefert Daten für dieCssSaving Ereignis.
type: docs
weight: 4620
url: /de/net/aspose.words.saving/csssavingargs/
---
## CssSavingArgs class

Liefert Daten für die[`CssSaving`](../icsssavingcallback/csssaving/) Ereignis.

```csharp
public class CssSavingArgs
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [CssStream](../../aspose.words.saving/csssavingargs/cssstream/) { get; set; } | Ermöglicht die Angabe des Streams, in dem die CSS-Informationen gespeichert werden. |
| [Document](../../aspose.words.saving/csssavingargs/document/) { get; } | Ruft das aktuell gespeicherte Dokumentobjekt ab. |
| [IsExportNeeded](../../aspose.words.saving/csssavingargs/isexportneeded/) { get; set; } | Ermöglicht die Angabe, ob das CSS in eine Datei exportiert und in ein HTML-Dokument eingebettet wird. Standard ist`Stimmt` . Wenn diese Eigenschaft ist`FALSCH` , werden die CSS-Informationen nicht in einer CSS-Datei gespeichert und nicht in ein HTML-Dokument eingebettet. |
| [KeepCssStreamOpen](../../aspose.words.saving/csssavingargs/keepcssstreamopen/) { get; set; } | Gibt an, ob Aspose.Words den Stream offen halten oder nach dem Speichern einer CSS-Information schließen soll. |

### Bemerkungen

Wenn Aspose.Words ein Dokument im HTML-Format speichert, speichert es standardmäßig CSS-Informationen inline (als Wert der **Stil** Attribut auf jedem Element).

`CssSavingArgs` ermöglicht das Speichern von CSS-Informationen in einer Datei, indem Sie Ihr eigenes Stream-Objekt bereitstellen.

Verwenden Sie zum Speichern von CSS im Stream die[`CssStream`](./cssstream/) Eigentum.

Um das Speichern von CSS in einer Datei und das Einbetten in ein HTML-Dokument zu unterdrücken, verwenden Sie die[`IsExportNeeded`](./isexportneeded/) Eigentum.

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

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


