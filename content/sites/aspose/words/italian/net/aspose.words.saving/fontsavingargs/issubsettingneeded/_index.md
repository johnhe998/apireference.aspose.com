---
title: FontSavingArgs.IsSubsettingNeeded
second_title: Aspose.Words per .NET API Reference
description: FontSavingArgs proprietà. Consente di specificare se il font corrente verrà inserito in un sottoinsieme prima dellesportazione come risorsa font.
type: docs
weight: 70
url: /it/net/aspose.words.saving/fontsavingargs/issubsettingneeded/
---
## FontSavingArgs.IsSubsettingNeeded property

Consente di specificare se il font corrente verrà inserito in un sottoinsieme prima dell'esportazione come risorsa font.

```csharp
public bool IsSubsettingNeeded { get; set; }
```

### Osservazioni

I caratteri possono essere esportati come file di caratteri originali completi o impostati in sottoinsiemi per includere solo i caratteri utilizzati nel documento. Il sottoinsieme consente di ridurre la dimensione della risorsa del carattere risultante.

Per impostazione predefinita, Aspose.Words decide se eseguire il subsetting o meno confrontando la dimensione del file del font originale con quella specificata in[`FontResourcesSubsettingSizeThreshold`](../../htmlsaveoptions/fontresourcessubsettingsizethreshold/) . È possibile ignorare questo comportamento per i singoli caratteri impostando il`IsSubsettingNeeded` proprietà.

### Esempi

Mostra come definire una logica personalizzata per l'esportazione dei caratteri durante il salvataggio in HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Configura un oggetto SaveOptions per esportare i caratteri in file separati.
    // Imposta una richiamata che gestirà il salvataggio dei caratteri in modo personalizzato.
    HtmlSaveOptions options = new HtmlSaveOptions
    {
        ExportFontResources = true,
        FontSavingCallback = new HandleFontSaving()
    };

    // La richiamata esporterà i file .ttf e li salverà insieme al documento di output.
    doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveExportedFonts.html", options);

    foreach (string fontFilename in Array.FindAll(Directory.GetFiles(ArtifactsDir), s => s.EndsWith(".ttf")))
    {
        Console.WriteLine(fontFilename);
    }

/// <summary>
/// Stampa le informazioni sui caratteri esportati e li salva nella stessa cartella di sistema locale del file .html di output.
/// </summary>
public class HandleFontSaving : IFontSavingCallback
{
    void IFontSavingCallback.FontSaving(FontSavingArgs args)
    {
        Console.Write($"Font:\t{args.FontFamilyName}");
        if (args.Bold) Console.Write(", bold");
        if (args.Italic) Console.Write(", italic");
        Console.WriteLine($"\nSource:\t{args.OriginalFileName}, {args.OriginalFileSize} bytes\n");

        // Possiamo anche accedere al documento sorgente da qui.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        Assert.True(args.IsExportNeeded);
        Assert.True(args.IsSubsettingNeeded);

        // Esistono due modi per salvare un font esportato.
        // 1 - Salvalo in una posizione del file system locale:
        args.FontFileName = args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last();

        // 2 - Salvalo in un flusso:
        args.FontStream =
            new FileStream(ArtifactsDir + args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last(), FileMode.Create);
        Assert.False(args.KeepFontStreamOpen);
    }
}
```

### Guarda anche

* class [FontSavingArgs](../)
* spazio dei nomi [Aspose.Words.Saving](../../fontsavingargs/)
* assemblea [Aspose.Words](../../../)


