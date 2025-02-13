---
title: HtmlSaveOptions.CssStyleSheetFileName
second_title: Aspose.Words per .NET API Reference
description: HtmlSaveOptions proprietà. Specifica il percorso e il nome del file CSS Cascading Style Sheet scritto quando un documento viene esportato in HTML. Il valore predefinito è una stringa vuota.
type: docs
weight: 50
url: /it/net/aspose.words.saving/htmlsaveoptions/cssstylesheetfilename/
---
## HtmlSaveOptions.CssStyleSheetFileName property

Specifica il percorso e il nome del file CSS (Cascading Style Sheet) scritto quando un documento viene esportato in HTML. Il valore predefinito è una stringa vuota.

```csharp
public string CssStyleSheetFileName { get; set; }
```

### Osservazioni

Questa proprietà ha effetto solo quando si salva un documento in formato HTML e viene richiesto un foglio di stile CSS esterno utilizzando[`CssStyleSheetType`](../cssstylesheettype/).

Se questa proprietà è vuota, il file CSS verrà salvato nella stessa cartella e con lo stesso nome del documento HTML ma con estensione ".css".

Se in questa proprietà viene specificato solo il percorso ma nessun nome file, il file CSS verrà salvato nella cartella specificata e avrà lo stesso nome del documento HTML ma con estensione ".css".

Se la cartella specificata da questa proprietà non esiste, verrà creata automaticamente prima del salvataggio del file CSS .

Un altro modo per specificare una cartella in cui viene salvato il file CSS esterno è utilizzare[`ResourceFolder`](../resourcefolder/) .

### Esempi

Mostra come lavorare con i fogli di stile CSS creati da una conversione HTML.

```csharp
public void ExternalCssFilenames()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Crea un oggetto "HtmlFixedSaveOptions", che possiamo passare al metodo "Save" del documento
    // per modificare il modo in cui convertiamo il documento in HTML.
    HtmlSaveOptions options = new HtmlSaveOptions();

    // Imposta la proprietà "CssStylesheetType" su "CssStyleSheetType.External" su
    // accompagna un documento HTML salvato con un file di foglio di stile CSS esterno.
    options.CssStyleSheetType = CssStyleSheetType.External;

    // Di seguito sono riportati due modi per specificare directory e nomi di file per i fogli di stile CSS di output.
    // 1 - Usa la proprietà "CssStyleSheetFileName" per assegnare un nome file al nostro foglio di stile:
    options.CssStyleSheetFileName = ArtifactsDir + "SavingCallback.ExternalCssFilenames.css";

    // 2 - Usa un callback personalizzato per nominare il nostro foglio di stile:
    options.CssSavingCallback =
        new CustomCssSavingCallback(ArtifactsDir + "SavingCallback.ExternalCssFilenames.css", true, false);

    doc.Save(ArtifactsDir + "SavingCallback.ExternalCssFilenames.html", options);
}

/// <summary>
/// Imposta un nome file personalizzato, insieme ad altri parametri per un foglio di stile CSS esterno.
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
        // Possiamo accedere all'intero documento sorgente tramite la proprietà "Documento".
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

### Guarda anche

* class [HtmlSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlsaveoptions/)
* assemblea [Aspose.Words](../../../)


