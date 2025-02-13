---
title: XamlFlowSaveOptions.ImagesFolder
second_title: Aspose.Words per .NET API Reference
description: XamlFlowSaveOptions proprietà. Specifica la cartella fisica in cui vengono salvate le immagini durante lesportazione di un documento in formato XAML. Limpostazione predefinita è una stringa vuota.
type: docs
weight: 30
url: /it/net/aspose.words.saving/xamlflowsaveoptions/imagesfolder/
---
## XamlFlowSaveOptions.ImagesFolder property

Specifica la cartella fisica in cui vengono salvate le immagini durante l'esportazione di un documento in formato XAML. L'impostazione predefinita è una stringa vuota.

```csharp
public string ImagesFolder { get; set; }
```

### Osservazioni

Quando salvi un[`Document`](../../../aspose.words/document/) in formato XAML, Aspose.Words deve salvare tutte le immagini incorporate nel documento come file autonomi.`ImagesFolder` consente di specificare dove verranno salvate le immagini e[`ImagesFolderAlias`](../imagesfolderalias/) permette di specificare come verranno costruiti gli URI dell'immagine.

Se si salva un documento in un file e si fornisce un nome file, Aspose.Words, per impostazione predefinita, salva le immagini nella stessa cartella in cui è salvato il file del documento. Uso`ImagesFolder` per ignorare questo comportamento.

Se salvi un documento in uno stream, Aspose.Words non ha una cartella in cui salvare le immagini, , ma deve comunque salvare le immagini da qualche parte. In questo caso, è necessario specificare una cartella accessibile nel file`ImagesFolder` proprietà o fornire flussi personalizzati tramite the[`ImageSavingCallback`](../imagesavingcallback/) gestore di eventi.

### Esempi

Mostra come stampare i nomi dei file delle immagini collegate create durante la conversione di un documento in formato .xaml in formato flusso.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ImageUriPrinter callback = new ImageUriPrinter(ArtifactsDir + "XamlFlowImageFolderAlias");

    // Crea un oggetto "XamlFlowSaveOptions", che possiamo passare al metodo "Save" del documento
    // per modificare il modo in cui salviamo il documento nel formato di salvataggio XAML.
    XamlFlowSaveOptions options = new XamlFlowSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFlow, options.SaveFormat);

    // Utilizzare la proprietà "ImagesFolder" per assegnare una cartella nel file system locale in cui
    // Aspose.Words salverà tutte le immagini collegate del documento.
    options.ImagesFolder = ArtifactsDir + "XamlFlowImageFolder";

    // Usa la proprietà "ImagesFolderAlias" per usare questa cartella
    // quando si costruiscono URI di immagine invece del nome della cartella delle immagini.
    options.ImagesFolderAlias = ArtifactsDir + "XamlFlowImageFolderAlias";

    options.ImageSavingCallback = callback;

    // Una cartella specificata da "ImagesFolderAlias" dovrà contenere le risorse invece di "ImagesFolder".
    // Dobbiamo assicurarci che la cartella esista prima che i flussi di callback possano inserirvi le proprie risorse.
    Directory.CreateDirectory(options.ImagesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFlowSaveOptions.ImageFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine($"{callback.ImagesFolderAlias}/{resource}");

/// <summary>
/// Conta e stampa i nomi dei file delle immagini mentre il loro documento principale viene convertito in formato flusso .xaml.
/// </summary>
private class ImageUriPrinter : IImageSavingCallback
{
    public ImageUriPrinter(string imagesFolderAlias)
    {
        ImagesFolderAlias = imagesFolderAlias;
        Resources = new List<string>();
    }

    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        Resources.Add(args.ImageFileName);

        // Se avessimo specificato un alias di cartella immagine, avremmo anche bisogno
        // per reindirizzare ogni flusso per inserire la sua immagine nella cartella alias.
        args.ImageStream = new FileStream($"{ImagesFolderAlias}/{args.ImageFileName}", FileMode.Create);
        args.KeepImageStreamOpen = false;
    }

    public string ImagesFolderAlias { get; }
    public List<string> Resources { get; }
}
```

### Guarda anche

* class [XamlFlowSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../xamlflowsaveoptions/)
* assemblea [Aspose.Words](../../../)


