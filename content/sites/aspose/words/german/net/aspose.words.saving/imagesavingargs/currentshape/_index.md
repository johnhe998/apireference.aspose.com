---
title: ImageSavingArgs.CurrentShape
second_title: Aspose.Words für .NET-API-Referenz
description: ImageSavingArgs eigendom. Ruft die abShapeBase Objekt das der zu speichernden Form oder Gruppenform entspricht.
type: docs
weight: 10
url: /de/net/aspose.words.saving/imagesavingargs/currentshape/
---
## ImageSavingArgs.CurrentShape property

Ruft die ab[`ShapeBase`](../../../aspose.words.drawing/shapebase/) Objekt, das der zu speichernden Form oder Gruppenform entspricht.

```csharp
public ShapeBase CurrentShape { get; }
```

### Bemerkungen

[`IImageSavingCallback`](../../iimagesavingcallback/) kann ausgelöst werden, während entweder eine Form oder eine Gruppenform gespeichert wird. Deshalb hat die Eigenschaft[`ShapeBase`](../../../aspose.words.drawing/shapebase/) Typ. Sie können überprüfen, ob es sich um eine Gruppenform handelt, indem Sie vergleichen[`ShapeType`](../../../aspose.words.drawing/shapebase/shapetype/) mitGroup oder indem Sie es in eine der abgeleiteten Klassen umwandeln: [`Shape`](../../../aspose.words.drawing/shape/) oder[`GroupShape`](../../../aspose.words.drawing/groupshape/).

Aspose.Words verwendet den Dateinamen des Dokuments und eine eindeutige Nummer, um einen eindeutigen Dateinamen für jedes im Dokument gefundene Bild zu generieren. Du kannst den ... benutzen`CurrentShape` -Eigenschaft zum Generieren eines "besseren" Dateinamens durch Untersuchen von Formeigenschaften wie z[`Title`](../../../aspose.words.drawing/imagedata/title/) (nur Form),[`SourceFullName`](../../../aspose.words.drawing/imagedata/sourcefullname/) (Nur Form) und[`Name`](../../../aspose.words.drawing/shapebase/name/)Natürlich können Sie Dateinamen mit beliebigen anderen Eigenschaften oder Kriterien erstellen , aber beachten Sie, dass untergeordnete Dateinamen innerhalb des Exportvorgangs eindeutig sein müssen.

Einige Bilder im Dokument sind möglicherweise nicht verfügbar. Um die Bildverfügbarkeit zu prüfen, verwenden Sie [`IsImageAvailable`](../isimageavailable/) Eigentum.

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

* class [ShapeBase](../../../aspose.words.drawing/shapebase/)
* class [ImageSavingArgs](../)
* namensraum [Aspose.Words.Saving](../../imagesavingargs/)
* Montage [Aspose.Words](../../../)


