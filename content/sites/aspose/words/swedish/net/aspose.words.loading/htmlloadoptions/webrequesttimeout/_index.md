---
title: HtmlLoadOptions.WebRequestTimeout
second_title: Aspose.Words för .NET API Referens
description: HtmlLoadOptions fast egendom. Antalet millisekunder som ska vänta innan webbförfrågan timeout. Standardvärdet är 100 000 millisekunder 100 sekunder.
type: docs
weight: 70
url: /sv/net/aspose.words.loading/htmlloadoptions/webrequesttimeout/
---
## HtmlLoadOptions.WebRequestTimeout property

Antalet millisekunder som ska vänta innan webbförfrågan timeout. Standardvärdet är 100 000 millisekunder (100 sekunder).

```csharp
public int WebRequestTimeout { get; set; }
```

### Anmärkningar

Antalet millisekunder som Aspose.Words väntar på ett svar vid laddning av externa resurser (bilder, style sheets) länkade i HTML- och MHTML-dokument.

### Exempel

Visar hur du ställer in en tidsgräns för webbförfrågningar när du laddar ett dokument med externa resurser länkade av URL:er.

```csharp
{
    // Skapa ett nytt HtmlLoadOptions-objekt och verifiera dess timeout-tröskel för en webbförfrågan.
    HtmlLoadOptions options = new HtmlLoadOptions();

    // När du laddar ett HTML-dokument med resurser som är externt länkade av en webbadress-URL,
    // Aspose.Words kommer att avbryta webbförfrågningar som inte kan hämta resurserna inom denna tidsgräns, i millisekunder.
    Assert.AreEqual(100000, options.WebRequestTimeout);

    // Ställ in en WarningCallback som kommer att registrera alla varningar som inträffar under laddning.
    ListDocumentWarnings warningCallback = new ListDocumentWarnings();
    options.WarningCallback = warningCallback;

    // Ladda ett sådant dokument och verifiera att en form med bilddata har skapats.
    // Den här länkade bilden kommer att kräva en webbförfrågan för att laddas, som måste slutföras inom vår tidsgräns.
    string html = $@"
        <html>
            <img src=""{ImageUrl}"" alt=""Aspose logo"" style=""width:400px;height:400px;"">
        </html>
    ";

    // Ställ in en orimlig tidsgräns och försök ladda dokumentet igen.
    options.WebRequestTimeout = 0;
    Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), options);
    Assert.AreEqual(2, warningCallback.Warnings().Count);

    // En webbförfrågan som inte lyckas få en bild inom tidsgränsen kommer fortfarande att producera en bild.
    // Bilden kommer dock att vara det röda "x" som vanligtvis betyder att bilder saknas.
    Shape imageShape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
    Assert.AreEqual(924, imageShape.ImageData.ImageBytes.Length);

    // Vi kan också konfigurera en anpassad återuppringning för att ta upp eventuella varningar från tidsgränsade webbförfrågningar.
    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[0].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[0].WarningType);
    Assert.AreEqual($"Couldn't load a resource from \'{ImageUrl}\'.", warningCallback.Warnings()[0].Description);

    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[1].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[1].WarningType);
    Assert.AreEqual("Image has been replaced with a placeholder.", warningCallback.Warnings()[1].Description);

    doc.Save(ArtifactsDir + "HtmlLoadOptions.WebRequestTimeout.docx");
}

/// <summary>
/// Lagrar alla varningar som inträffar under en dokumentladdningsoperation i en lista.
/// </summary>
private class ListDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        mWarnings.Add(info);
    }

    public List<WarningInfo> Warnings() { 
        return mWarnings;
    }

    private readonly List<WarningInfo> mWarnings = new List<WarningInfo>();
}
```

### Se även

* class [HtmlLoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../htmlloadoptions/)
* hopsättning [Aspose.Words](../../../)


