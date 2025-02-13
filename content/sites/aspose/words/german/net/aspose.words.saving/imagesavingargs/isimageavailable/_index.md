---
title: ImageSavingArgs.IsImageAvailable
second_title: Aspose.Words für .NET-API-Referenz
description: ImageSavingArgs eigendom. gibt zurückStimmt wenn das aktuelle Bild für den Export verfügbar ist.
type: docs
weight: 50
url: /de/net/aspose.words.saving/imagesavingargs/isimageavailable/
---
## ImageSavingArgs.IsImageAvailable property

gibt zurück`Stimmt` wenn das aktuelle Bild für den Export verfügbar ist.

```csharp
public bool IsImageAvailable { get; }
```

### Bemerkungen

Einige Bilder im Dokument können beispielsweise nicht verfügbar sein, weil image verlinkt ist und der Link nicht zugänglich ist oder nicht auf ein gültiges Bild verweist. In diesem Fall exportiert Aspose.Words ein Symbol mit einem roten Kreuz. Diese Eigenschaft gibt zurück`Stimmt` wenn das Originalbild verfügbar ist; kehrt zurück`FALSCH` wenn das ursprüngliche -Bild nicht verfügbar ist, wird ein "kein Bild"-Symbol zum Speichern angeboten.

Beim Speichern einer Gruppenform oder einer Form, die kein Bild benötigt, ist diese Eigenschaft immer`Stimmt`.

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

* property [CurrentShape](../currentshape/)
* class [ImageSavingArgs](../)
* namensraum [Aspose.Words.Saving](../../imagesavingargs/)
* Montage [Aspose.Words](../../../)


