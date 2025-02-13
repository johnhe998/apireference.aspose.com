---
title: ImageSavingArgs.KeepImageStreamOpen
second_title: Aspose.Words für .NET-API-Referenz
description: ImageSavingArgs eigendom. Gibt an ob Aspose.Words den Stream offen halten oder schließen soll nachdem ein Bild gespeichert wurde.
type: docs
weight: 60
url: /de/net/aspose.words.saving/imagesavingargs/keepimagestreamopen/
---
## ImageSavingArgs.KeepImageStreamOpen property

Gibt an, ob Aspose.Words den Stream offen halten oder schließen soll, nachdem ein Bild gespeichert wurde.

```csharp
public bool KeepImageStreamOpen { get; set; }
```

### Bemerkungen

Standard ist`FALSCH` und Aspose.Words schließt den von Ihnen bereitgestellten Stream in der[`ImageStream`](../imagestream/) Eigenschaft, nachdem ein Bild hineingeschrieben wurde. Angeben`Stimmt` um den Strom offen zu halten.

### Beispiele

Zeigt, wie ein Callback zum Speichern von Bildern in einen HTML-Konvertierungsprozess einbezogen wird.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Wenn wir das Dokument im HTML-Format speichern, können wir ein SaveOptions-Objekt übergeben, um einen Rückruf festzulegen
    // um den Bildspeicherprozess anzupassen.
    HtmlSaveOptions options = new HtmlSaveOptions();
    options.ImageSavingCallback = new ImageShapePrinter();

    doc.Save(ArtifactsDir + "HtmlSaveOptions.ImageSavingCallback.html", options);
}

/// <summary>
/// Druckt die Eigenschaften jedes Bildes, während der Speicherprozess es in einer Bilddatei im lokalen Dateisystem speichert
/// während des Exports eines Dokuments nach HTML.
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

### Siehe auch

* class [ImageSavingArgs](../)
* namensraum [Aspose.Words.Saving](../../imagesavingargs/)
* Montage [Aspose.Words](../../../)


