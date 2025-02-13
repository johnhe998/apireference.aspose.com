---
title: ImageSavingArgs.ImageStream
second_title: Aspose.Words per .NET API Reference
description: ImageSavingArgs proprietà. Consente di specificare lo stream in cui verrà salvata limmagine.
type: docs
weight: 40
url: /it/net/aspose.words.saving/imagesavingargs/imagestream/
---
## ImageSavingArgs.ImageStream property

Consente di specificare lo stream in cui verrà salvata l'immagine.

```csharp
public Stream ImageStream { get; set; }
```

### Osservazioni

Questa proprietà consente di salvare le immagini negli stream anziché nei file durante l'HTML.

Il valore predefinito è`nullo` . Quando questa proprietà è`nullo` , l'immagine verrà salvata in un file specificato in[`ImageFileName`](../imagefilename/) proprietà.

Usando[`IImageSavingCallback`](../../iimagesavingcallback/) non puoi sostituire un'immagine con un'altra. È inteso solo per controllare la posizione in cui salvare le immagini.

### Esempi

Mostra come coinvolgere un callback per il salvataggio di immagini in un processo di conversione HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Quando salviamo il documento in HTML, possiamo passare un oggetto SaveOptions per designare un callback
    // per personalizzare il processo di salvataggio dell'immagine.
    HtmlSaveOptions options = new HtmlSaveOptions();
    options.ImageSavingCallback = new ImageShapePrinter();

    doc.Save(ArtifactsDir + "HtmlSaveOptions.ImageSavingCallback.html", options);
}

/// <summary>
/// Stampa le proprietà di ciascuna immagine mentre il processo di salvataggio la salva in un file immagine nel file system locale
/// durante l'esportazione di un documento in HTML.
/// </summary>
private class ImageShapePrinter : IImageSavingCallback
{
    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        args.KeepImageStreamOpen = false;
        Assert.True(args.IsImageAvailable);

        Console.WriteLine($"{args.Document.OriginalFileName.Split('\\').Last()} Image #{++mImageCount}");

        LayoutCollector layoutCollector = new LayoutCollector(args.Document);

        Console.WriteLine($"\tOn page:\t{layoutCollector.GetStartPageIndex(args.CurrentShape)}");
        Console.WriteLine($"\tDimensions:\t{args.CurrentShape.Bounds}");
        Console.WriteLine($"\tAlignment:\t{args.CurrentShape.VerticalAlignment}");
        Console.WriteLine($"\tWrap type:\t{args.CurrentShape.WrapType}");
        Console.WriteLine($"Output filename:\t{args.ImageFileName}\n");
    }

    private int mImageCount;
}
```

### Guarda anche

* class [ImageSavingArgs](../)
* spazio dei nomi [Aspose.Words.Saving](../../imagesavingargs/)
* assemblea [Aspose.Words](../../../)


