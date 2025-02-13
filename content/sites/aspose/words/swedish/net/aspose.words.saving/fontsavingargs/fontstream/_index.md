---
title: FontSavingArgs.FontStream
second_title: Aspose.Words för .NET API Referens
description: FontSavingArgs fast egendom. Tillåter att ange strömmen där teckensnittet ska sparas.
type: docs
weight: 50
url: /sv/net/aspose.words.saving/fontsavingargs/fontstream/
---
## FontSavingArgs.FontStream property

Tillåter att ange strömmen där teckensnittet ska sparas.

```csharp
public Stream FontStream { get; set; }
```

### Anmärkningar

Den här egenskapen låter dig spara teckensnitt i strömmar istället för filer under HTML-export.

Standardvärdet är`null` . När denna fastighet är`null` , kommer teckensnittet att sparas i en fil som anges i[`FontFileName`](../fontfilename/) fast egendom.

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


