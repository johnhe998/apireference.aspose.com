---
title: PageSavingArgs.KeepPageStreamOpen
second_title: Aspose.Words för .NET API Referens
description: PageSavingArgs fast egendom. Anger om Aspose.Words ska hålla strömmen öppen eller stänga den efter att en dokumentsida har sparats.
type: docs
weight: 20
url: /sv/net/aspose.words.saving/pagesavingargs/keeppagestreamopen/
---
## PageSavingArgs.KeepPageStreamOpen property

Anger om Aspose.Words ska hålla strömmen öppen eller stänga den efter att en dokumentsida har sparats.

```csharp
public bool KeepPageStreamOpen { get; set; }
```

### Anmärkningar

Standard är`falsk` och Aspose.Words kommer att stänga strömmen du angav i[`PageStream`](../pagestream/) egenskap efter att ha skrivit en dokumentsida i den. Specificera`Sann` för att hålla strömmen öppen.

### Exempel

Visar hur man använder en återuppringning för att spara ett dokument i HTML sida för sida.

```csharp
public void PageFileNames()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("Page 1.");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 2.");
    builder.InsertImage(ImageDir + "Logo.jpg");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 3.");

    // Skapa ett "HtmlFixedSaveOptions"-objekt, som vi kan skicka till dokumentets "Spara"-metod
    // för att ändra hur vi konverterar dokumentet till HTML.
    HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions();

    // Vi kommer att spara varje sida i detta dokument till en separat HTML-fil i det lokala filsystemet.
    // Ställ in en återuppringning som låter oss namnge varje utdata-HTML-dokument.
    htmlFixedSaveOptions.PageSavingCallback = new CustomFileNamePageSavingCallback();

    doc.Save(ArtifactsDir + "SavingCallback.PageFileNames.html", htmlFixedSaveOptions);

    string[] filePaths = Directory.GetFiles(ArtifactsDir).Where(
        s => s.StartsWith(ArtifactsDir + "SavingCallback.PageFileNames.Page_")).OrderBy(s => s).ToArray();

    Assert.AreEqual(3, filePaths.Length);
}

/// <summary>
/// Sparar alla sidor till en fil och katalog som anges i.
/// </summary>
private class CustomFileNamePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        string outFileName = $"{ArtifactsDir}SavingCallback.PageFileNames.Page_{args.PageIndex}.html";

        // Nedan finns två sätt att ange var Aspose.Words kommer att spara varje sida i dokumentet.
        // 1 - Ange ett filnamn för utdatafilen:
        args.PageFileName = outFileName;

        // 2 - Skapa en anpassad ström för utdatafilen:
        args.PageStream = new FileStream(outFileName, FileMode.Create);

        Assert.False(args.KeepPageStreamOpen);
    }
}
```

### Se även

* class [PageSavingArgs](../)
* namnutrymme [Aspose.Words.Saving](../../pagesavingargs/)
* hopsättning [Aspose.Words](../../../)


