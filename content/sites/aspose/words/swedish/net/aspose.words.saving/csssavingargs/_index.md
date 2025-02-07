---
title: Class CssSavingArgs
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.CssSavingArgs klass. Tillhandahåller data förCssSaving händelse.
type: docs
weight: 4620
url: /sv/net/aspose.words.saving/csssavingargs/
---
## CssSavingArgs class

Tillhandahåller data för[`CssSaving`](../icsssavingcallback/csssaving/) händelse.

```csharp
public class CssSavingArgs
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [CssStream](../../aspose.words.saving/csssavingargs/cssstream/) { get; set; } | Tillåter att ange strömmen där CSS-informationen ska sparas. |
| [Document](../../aspose.words.saving/csssavingargs/document/) { get; } | Hämtar dokumentobjektet som för närvarande sparas. |
| [IsExportNeeded](../../aspose.words.saving/csssavingargs/isexportneeded/) { get; set; } | Tillåter att ange om CSS ska exporteras till fil och bäddas in i HTML-dokument. Standard är`Sann` . När den här egenskapen är`falsk` , kommer CSS-informationen inte att sparas i en CSS-fil och kommer inte att bäddas in i HTML-dokument. |
| [KeepCssStreamOpen](../../aspose.words.saving/csssavingargs/keepcssstreamopen/) { get; set; } | Anger om Aspose.Words ska hålla strömmen öppen eller stänga den efter att ha sparat en CSS-information. |

### Anmärkningar

Som standard, när Aspose.Words sparar ett dokument till HTML, sparas CSS-information inline (som ett värde för **stil** attribut på varje element).

`CssSavingArgs` gör det möjligt att spara CSS-information i en fil genom att tillhandahålla ditt eget strömobjekt.

För att spara CSS i stream, använd[`CssStream`](./cssstream/) fast egendom.

För att undertrycka att spara CSS i en fil och bädda in i HTML-dokument använder du[`IsExportNeeded`](./isexportneeded/) fast egendom.

### Exempel

Visar hur man arbetar med CSS-formatmallar som en HTML-konvertering skapar.

```csharp
public void ExternalCssFilenames()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Skapa ett "HtmlFixedSaveOptions"-objekt, som vi kan skicka till dokumentets "Spara"-metod
    // för att ändra hur vi konverterar dokumentet till HTML.
    HtmlSaveOptions options = new HtmlSaveOptions();

    // Ställ in egenskapen "CssStylesheetType" till "CssStyleSheetType.External" till
    // åtfölja ett sparat HTML-dokument med en extern CSS-formatmallsfil.
    options.CssStyleSheetType = CssStyleSheetType.External;

    // Nedan finns två sätt att ange kataloger och filnamn för CSS-formatmallar.
    // 1 - Använd egenskapen "CssStyleSheetFileName" för att tilldela ett filnamn till vår stilmall:
    options.CssStyleSheetFileName = ArtifactsDir + "SavingCallback.ExternalCssFilenames.css";

    // 2 - Använd en anpassad återuppringning för att namnge vår stilmall:
    options.CssSavingCallback =
        new CustomCssSavingCallback(ArtifactsDir + "SavingCallback.ExternalCssFilenames.css", true, false);

    doc.Save(ArtifactsDir + "SavingCallback.ExternalCssFilenames.html", options);
}

/// <summary>
/// Ställer in ett anpassat filnamn, tillsammans med andra parametrar för en extern CSS-stilmall.
/// </summary>
private class CustomCssSavingCallback : ICssSavingCallback
{
    public CustomCssSavingCallback(string cssDocFilename, bool isExportNeeded, bool keepCssStreamOpen)
    {
        mCssTextFileName = cssDocFilename;
        mIsExportNeeded = isExportNeeded;
        mKeepCssStreamOpen = keepCssStreamOpen;
    }

    public void CssSaving(CssSavingArgs args)
    {
        // Vi kan komma åt hela källdokumentet via egenskapen "Dokument".
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        args.CssStream = new FileStream(mCssTextFileName, FileMode.Create);
        args.IsExportNeeded = mIsExportNeeded;
        args.KeepCssStreamOpen = mKeepCssStreamOpen;

        Assert.True(args.CssStream.CanWrite);
    }

    private readonly string mCssTextFileName;
    private readonly bool mIsExportNeeded;
    private readonly bool mKeepCssStreamOpen;
}
```

### Se även

* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


