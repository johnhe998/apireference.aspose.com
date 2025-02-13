---
title: Interface IPageSavingCallback
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.IPageSavingCallback gränssnitt. Implementera detta gränssnitt om du vill styra hur Aspose.Words sparar separata sidor när sparar ett dokument i fasta sidformat.
type: docs
weight: 4920
url: /sv/net/aspose.words.saving/ipagesavingcallback/
---
## IPageSavingCallback interface

Implementera detta gränssnitt om du vill styra hur Aspose.Words sparar separata sidor när sparar ett dokument i fasta sidformat.

```csharp
public interface IPageSavingCallback
```

## Metoder

| namn | Beskrivning |
| --- | --- |
| [PageSaving](../../aspose.words.saving/ipagesavingcallback/pagesaving/)(PageSavingArgs) | Anropas när Aspose.Words sparar en separat sida till fasta sidformat. |

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

* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


