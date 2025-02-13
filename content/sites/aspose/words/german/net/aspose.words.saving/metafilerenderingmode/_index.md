---
title: Enum MetafileRenderingMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.MetafileRenderingMode opsomming. Gibt an wie Aspose.Words WMF und EMFMetadateien rendern soll.
type: docs
weight: 5010
url: /de/net/aspose.words.saving/metafilerenderingmode/
---
## MetafileRenderingMode enumeration

Gibt an, wie Aspose.Words WMF- und EMF-Metadateien rendern soll.

```csharp
public enum MetafileRenderingMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| VectorWithFallback | `0` | Aspose.Words versucht, eine Metadatei als Vektorgrafik darzustellen. Wenn Aspose.Words einige der Metafile-Datensätze nicht korrekt in Vektorgrafiken rendern kann, rendert Aspose.Words diese Metadatei in eine Bitmap. |
| Vector | `1` | Aspose.Words rendert eine Metadatei als Vektorgrafik. |
| Bitmap | `2` | Aspose.Words ruft GDI+ auf, um eine Metadatei in eine Bitmap zu rendern, und speichert dann die Bitmap im Ausgabedokument. |

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

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


