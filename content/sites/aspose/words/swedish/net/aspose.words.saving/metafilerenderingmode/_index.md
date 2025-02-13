---
title: Enum MetafileRenderingMode
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.MetafileRenderingMode uppräkning. Anger hur Aspose.Words ska återge WMF och EMFmetafiler.
type: docs
weight: 5010
url: /sv/net/aspose.words.saving/metafilerenderingmode/
---
## MetafileRenderingMode enumeration

Anger hur Aspose.Words ska återge WMF- och EMF-metafiler.

```csharp
public enum MetafileRenderingMode
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| VectorWithFallback | `0` | Aspose.Words försöker rendera en metafil som vektorgrafik. Om Aspose.Words inte kan rendera några av metafilposterna korrekt till vektorgrafik så renderar Aspose.Words denna metafil till en bitmapp. |
| Vector | `1` | Aspose.Words återger en metafil som vektorgrafik. |
| Bitmap | `2` | Aspose.Words anropar GDI+ för att rendera en metafil till en bitmapp och sparar sedan bitmappen till utdatadokumentet. |

### Exempel

Visar lade till en reserv till bitmappsrendering och ändrade typ av varningar om metafilposter som inte stöds.

```csharp
{
    Document doc = new Document(MyDir + "WMF with image.docx");

    MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions();

    // Ställ in egenskapen "EmulateRasterOperations" till "false" för att falla tillbaka till bitmapp när
    // den stöter på en metafil, som kräver rasteroperationer för att rendera i utdata-PDF.
    metafileRenderingOptions.EmulateRasterOperations = false;

    // Ställ in egenskapen "RenderingMode" till "VectorWithFallback" för att försöka rendera varje metafil med vektorgrafik.
    metafileRenderingOptions.RenderingMode = MetafileRenderingMode.VectorWithFallback;

    // Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
    // för att ändra hur den metoden konverterar dokumentet till .PDF och tillämpar konfigurationen
    // i vårt MetafileRenderingOptions-objekt mot sparoperationen.
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
/// Skriver ut och samlar in formateringsförlustrelaterade varningar som uppstår när ett dokument sparas.
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

### Se även

* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


