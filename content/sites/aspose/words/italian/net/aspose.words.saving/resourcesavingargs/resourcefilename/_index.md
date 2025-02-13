---
title: ResourceSavingArgs.ResourceFileName
second_title: Aspose.Words per .NET API Reference
description: ResourceSavingArgs proprietà. Ottiene o imposta il nome del file senza percorso in cui verrà salvata la risorsa.
type: docs
weight: 30
url: /it/net/aspose.words.saving/resourcesavingargs/resourcefilename/
---
## ResourceSavingArgs.ResourceFileName property

Ottiene o imposta il nome del file (senza percorso) in cui verrà salvata la risorsa.

```csharp
public string ResourceFileName { get; set; }
```

### Osservazioni

Questa proprietà consente di ridefinire il modo in cui i nomi dei file di risorse vengono generati durante l'esportazione in HTML o SVG a pagina fissa.

Quando l'evento viene generato, questa proprietà contiene il nome del file che è stato generato da Aspose.Words. È possibile modificare il valore di questa proprietà per salvare la risorsa in un file diverso. Tieni presente che i nomi dei file devono essere univoci.

Aspose.Words genera automaticamente un nome file univoco per ogni risorsa durante l'esportazione di in formato HTML o SVG a pagina fissa. Il modo in cui viene generato il nome del file di risorse dipende dal fatto che il documento venga salvato in un file o in un flusso.

Quando si salva un documento in un file, il nome del file di risorse generato è simile a &lt;nome file base documento&gt;.&lt;numero immagine&gt;.&lt;estensione&gt;.

Quando si salva un documento in un flusso, il nome del file di risorse generato è simile a Aspose.Words.&lt;documento guida&gt;.&lt;numero immagine&gt;.&lt;estensione&gt;.

`ResourceFileName` deve contenere solo il nome del file senza il percorso. Aspose.Words determina il percorso per il salvataggio e il valore del`src` attributo per scrivere su una pagina fissa HTML o SVG utilizzando il nome del file del documento, il[`ResourcesFolder`](../../htmlfixedsaveoptions/resourcesfolder/) o[`ResourcesFolder`](../../svgsaveoptions/resourcesfolder/) e[`ResourcesFolderAlias`](../../htmlfixedsaveoptions/resourcesfolderalias/) o[`ResourcesFolderAlias`](../../svgsaveoptions/resourcesfolderalias/) proprietà.

[`ResourcesFolder`](../../htmlfixedsaveoptions/resourcesfolder/)[`ResourcesFolder`](../../svgsaveoptions/resourcesfolder/)[`ResourcesFolderAlias`](../../htmlfixedsaveoptions/resourcesfolderalias/)[`ResourcesFolderAlias`](../../svgsaveoptions/resourcesfolderalias/)

### Esempi

Mostra come utilizzare una richiamata per tenere traccia delle risorse esterne create durante la conversione di un documento in HTML.

```csharp
public void ResourceSavingCallback()
{
    Document doc = new Document(MyDir + "Bullet points with alternative font.docx");

    FontSavingCallback callback = new FontSavingCallback();

    HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
    {
        ResourceSavingCallback = callback
    };

    doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html", saveOptions);

    Console.WriteLine(callback.GetText());
}

private class FontSavingCallback : IResourceSavingCallback
{
    /// <summary>
    /// Chiamato quando Aspose.Words salva una risorsa esterna in una pagina HTML o SVG fissa.
    /// </summary>
    public void ResourceSaving(ResourceSavingArgs args)
    {
        mText.AppendLine($"Original document URI:\t{args.Document.OriginalFileName}");
        mText.AppendLine($"Resource being saved:\t{args.ResourceFileName}");
        mText.AppendLine($"Full uri after saving:\t{args.ResourceFileUri}\n");
    }

    public string GetText()
    {
        return mText.ToString();
    }

    private readonly StringBuilder mText = new StringBuilder();
}
```

### Guarda anche

* class [ResourceSavingArgs](../)
* spazio dei nomi [Aspose.Words.Saving](../../resourcesavingargs/)
* assemblea [Aspose.Words](../../../)


