---
title: XamlFlowSaveOptions.ImageSavingCallback
second_title: Aspose.Words per .NET API Reference
description: XamlFlowSaveOptions proprietà. Consente di controllare il modo in cui le immagini vengono salvate quando un documento viene salvato in XAML.
type: docs
weight: 20
url: /it/net/aspose.words.saving/xamlflowsaveoptions/imagesavingcallback/
---
## XamlFlowSaveOptions.ImageSavingCallback property

Consente di controllare il modo in cui le immagini vengono salvate quando un documento viene salvato in XAML.

```csharp
public IImageSavingCallback ImageSavingCallback { get; set; }
```

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

* interface [IImageSavingCallback](../../iimagesavingcallback/)
* class [XamlFlowSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../xamlflowsaveoptions/)
* assemblea [Aspose.Words](../../../)


