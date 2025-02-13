---
title: CssSavingArgs.CssStream
second_title: Aspose.Words per .NET API Reference
description: CssSavingArgs proprietà. Consente di specificare lo stream in cui verranno salvate le informazioni CSS.
type: docs
weight: 10
url: /it/net/aspose.words.saving/csssavingargs/cssstream/
---
## CssSavingArgs.CssStream property

Consente di specificare lo stream in cui verranno salvate le informazioni CSS.

```csharp
public Stream CssStream { get; set; }
```

### Osservazioni

Questa proprietà consente di salvare le informazioni CSS in uno stream.

Il valore predefinito è`nullo` Questa proprietà non impedisce il salvataggio delle informazioni CSS in un file o l'incorporamento di in un documento HTML. Per sopprimere l'esportazione CSS, utilizzare il file[`IsExportNeeded`](../isexportneeded/) proprietà.

Usando[`ICssSavingCallback`](../../icsssavingcallback/) non puoi sostituire CSS con un altro. È inteso solo per salvare CSS in un flusso.

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

* class [CssSavingArgs](../)
* spazio dei nomi [Aspose.Words.Saving](../../csssavingargs/)
* assemblea [Aspose.Words](../../../)


