---
title: FontSavingArgs.IsSubsettingNeeded
second_title: Aspose.Words för .NET API Referens
description: FontSavingArgs fast egendom. Tillåter att ange om det aktuella teckensnittet kommer att underordnas innan det exporteras som en teckensnittsresurs.
type: docs
weight: 70
url: /sv/net/aspose.words.saving/fontsavingargs/issubsettingneeded/
---
## FontSavingArgs.IsSubsettingNeeded property

Tillåter att ange om det aktuella teckensnittet kommer att underordnas innan det exporteras som en teckensnittsresurs.

```csharp
public bool IsSubsettingNeeded { get; set; }
```

### Anmärkningar

Teckensnitt kan exporteras som kompletta originalteckensnittsfiler eller underuppsättning för att endast inkludera de tecken som används i dokumentet. Delinställning gör det möjligt att minska den resulterande teckensnittsresursstorleken.

Som standard bestämmer Aspose.Words om det ska utföras delinställning eller inte genom att jämföra den ursprungliga teckensnittsfilstorleken med den som anges i[`FontResourcesSubsettingSizeThreshold`](../../htmlsaveoptions/fontresourcessubsettingsizethreshold/) . Du kan åsidosätta detta beteende för enskilda teckensnitt genom att ställa in`IsSubsettingNeeded` fast egendom.

### Exempel

Visar hur man definierar anpassad logik för att exportera teckensnitt när man sparar till HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Konfigurera ett SaveOptions-objekt för att exportera teckensnitt till separata filer.
    // Ställ in en återuppringning som kommer att hantera teckensnittssparande på ett anpassat sätt.
    HtmlSaveOptions options = new HtmlSaveOptions
    {
        ExportFontResources = true,
        FontSavingCallback = new HandleFontSaving()
    };

    // Återuppringningen kommer att exportera .ttf-filer och spara dem tillsammans med utdatadokumentet.
    doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveExportedFonts.html", options);

    foreach (string fontFilename in Array.FindAll(Directory.GetFiles(ArtifactsDir), s => s.EndsWith(".ttf")))
    {
        Console.WriteLine(fontFilename);
    }

/// <summary>
/// Skriver ut information om exporterade teckensnitt och sparar dem i samma lokala systemmapp som deras utdata .html.
/// </summary>
public class HandleFontSaving : IFontSavingCallback
{
    void IFontSavingCallback.FontSaving(FontSavingArgs args)
    {
        Console.Write($"Font:\t{args.FontFamilyName}");
        if (args.Bold) Console.Write(", bold");
        if (args.Italic) Console.Write(", italic");
        Console.WriteLine($"\nSource:\t{args.OriginalFileName}, {args.OriginalFileSize} bytes\n");

        // Vi kan också komma åt källdokumentet härifrån.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        Assert.True(args.IsExportNeeded);
        Assert.True(args.IsSubsettingNeeded);

        // Det finns två sätt att spara ett exporterat teckensnitt.
        // 1 - Spara den på en lokal filsystemsplats:
        args.FontFileName = args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last();

        // 2 - Spara det i en stream:
        args.FontStream =
            new FileStream(ArtifactsDir + args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last(), FileMode.Create);
        Assert.False(args.KeepFontStreamOpen);
    }
}
```

### Se även

* class [FontSavingArgs](../)
* namnutrymme [Aspose.Words.Saving](../../fontsavingargs/)
* hopsättning [Aspose.Words](../../../)


