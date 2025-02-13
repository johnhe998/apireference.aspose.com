---
title: Class MetafileRenderingOptions
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.MetafileRenderingOptions klass. Tillåter att ange ytterligare alternativ för metafilrendering.
type: docs
weight: 5020
url: /sv/net/aspose.words.saving/metafilerenderingoptions/
---
## MetafileRenderingOptions class

Tillåter att ange ytterligare alternativ för metafilrendering.

```csharp
public class MetafileRenderingOptions
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [MetafileRenderingOptions](metafilerenderingoptions/)() | Default_Constructor |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [EmfPlusDualRenderingMode](../../aspose.words.saving/metafilerenderingoptions/emfplusdualrenderingmode/) { get; set; } | Hämtar eller ställer in ett värde som bestämmer hur EMF+ Dual-metafiler ska renderas. |
| [EmulateRasterOperations](../../aspose.words.saving/metafilerenderingoptions/emulaterasteroperations/) { get; set; } | Hämtar eller ställer in ett värde som avgör om rasteroperationerna ska emuleras eller inte. |
| [RenderingMode](../../aspose.words.saving/metafilerenderingoptions/renderingmode/) { get; set; } | Hämtar eller ställer in ett värde som bestämmer hur metafilbilder ska renderas. |
| [ScaleWmfFontsToMetafileSize](../../aspose.words.saving/metafilerenderingoptions/scalewmffontstometafilesize/) { get; set; } | Hämtar eller ställer in ett värde som avgör om teckensnitt ska skalas eller inte i WMF-metafil enligt metafilstorlek på sidan. |
| [UseEmfEmbeddedToWmf](../../aspose.words.saving/metafilerenderingoptions/useemfembeddedtowmf/) { get; set; } | Hämtar eller ställer in ett värde som bestämmer hur WMF-metafiler med inbäddade EMF-metafiler ska renderas. |

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


