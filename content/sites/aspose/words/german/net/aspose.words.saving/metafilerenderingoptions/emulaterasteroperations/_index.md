---
title: MetafileRenderingOptions.EmulateRasterOperations
second_title: Aspose.Words für .NET-API-Referenz
description: MetafileRenderingOptions eigendom. Ruft einen Wert ab oder legt ihn fest der bestimmt ob die Rasteroperationen emuliert werden sollen oder nicht.
type: docs
weight: 30
url: /de/net/aspose.words.saving/metafilerenderingoptions/emulaterasteroperations/
---
## MetafileRenderingOptions.EmulateRasterOperations property

Ruft einen Wert ab oder legt ihn fest, der bestimmt, ob die Rasteroperationen emuliert werden sollen oder nicht.

```csharp
public bool EmulateRasterOperations { get; set; }
```

### Bemerkungen

In Metadateien könnten bestimmte Rasteroperationen verwendet werden. Sie können nicht direkt in Vektorgrafiken gerendert werden. Das Emulieren von Rasteroperationen erfordert eine teilweise Rasterung der resultierenden Vektorgrafiken, was sich auf die Renderingleistung der -Metadatei auswirken kann.

Wenn dieser Wert auf eingestellt ist`Stimmt`, Aspose.Words emuliert die Rasteroperationen. Die resultierende Ausgabe ist möglicherweise teilweise gerastert und die Leistung ist möglicherweise langsamer.

Wenn dieser Wert auf eingestellt ist`FALSCH`, Aspose.Words emuliert die Rasteroperationen nicht. Wenn Aspose.Words auf eine Rasteroperation in einer Metadatei stößt, greift es auf das Rendern der Metadatei in eine Bitmap zurück, indem es das -Betriebssystem verwendet.

Diese Option wird nur verwendet, wenn die Metadatei als Vektorgrafik gerendert wird.

Der Standardwert ist`Stimmt`.

### Beispiele

Shows hat einen Fallback zum Bitmap-Rendering hinzugefügt und die Art der Warnungen über nicht unterstützte Metadatei-Datensätze geändert.

```csharp
{
    Document doc = new Document(MyDir + "WMF with image.docx");

    MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions();

    // Setzen Sie die Eigenschaft "EmulateRasterOperations" auf "false", um auf Bitmap zurückzugreifen, wenn
    // Es trifft auf eine Metadatei, die Rasteroperationen zum Rendern in der Ausgabe-PDF erfordert.
    metafileRenderingOptions.EmulateRasterOperations = false;

    // Setzen Sie die Eigenschaft "RenderingMode" auf "VectorWithFallback", um zu versuchen, jede Metadatei mit Vektorgrafiken zu rendern.
    metafileRenderingOptions.RenderingMode = MetafileRenderingMode.VectorWithFallback;

    // Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
    // um zu ändern, wie diese Methode das Dokument in .PDF konvertiert und die Konfiguration anwendet
    // in unserem MetafileRenderingOptions-Objekt für den Speichervorgang.
    PdfSaveOptions saveOptions = new PdfSaveOptions();
    saveOptions.MetafileRenderingOptions = metafileRenderingOptions;

    HandleDocumentWarnings callback = new HandleDocumentWarnings();
    doc.WarningCallback = callback;

    doc.Save(ArtifactsDir + "PdfSaveOptions.HandleBinaryRasterWarnings.pdf", saveOptions);

    Assert.AreEqual(1, callback.Warnings.Count);
    Assert.AreEqual("'R2_XORPEN' binary raster operation is partly supported.",
        callback.Warnings[0].Description);
}

/// <summary>
/// Druckt und sammelt Formatierungsverlust-bezogene Warnungen, die beim Speichern eines Dokuments auftreten.
/// </summary>
public class HandleDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.MinorFormattingLoss)
        {
            Console.WriteLine("Unsupported operation: " + info.Description);
            Warnings.Warning(info);
        }
    }

    public WarningInfoCollection Warnings = new WarningInfoCollection();
}
```

### Siehe auch

* class [MetafileRenderingOptions](../)
* namensraum [Aspose.Words.Saving](../../metafilerenderingoptions/)
* Montage [Aspose.Words](../../../)


