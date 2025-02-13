---
title: ImageSavingArgs.Document
second_title: Aspose.Words per .NET API Reference
description: ImageSavingArgs proprietà. Ottiene loggetto del documento attualmente in fase di salvataggio.
type: docs
weight: 20
url: /it/net/aspose.words.saving/imagesavingargs/document/
---
## ImageSavingArgs.Document property

Ottiene l'oggetto del documento attualmente in fase di salvataggio.

```csharp
public Document Document { get; }
```

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

* class [Document](../../../aspose.words/document/)
* class [ImageSavingArgs](../)
* spazio dei nomi [Aspose.Words.Saving](../../imagesavingargs/)
* assemblea [Aspose.Words](../../../)


