---
title: FontFallbackSettings.BuildAutomatic
second_title: Aspose.Words per .NET API Reference
description: FontFallbackSettings metodo. Crea automaticamente le impostazioni di fallback eseguendo la scansione dei caratteri disponibili.
type: docs
weight: 10
url: /it/net/aspose.words.fonts/fontfallbacksettings/buildautomatic/
---
## FontFallbackSettings.BuildAutomatic method

Crea automaticamente le impostazioni di fallback eseguendo la scansione dei caratteri disponibili.

```csharp
public void BuildAutomatic()
```

### Osservazioni

Questo metodo può produrre impostazioni di fallback non ottimali. I caratteri sono controllati da[ Intervallo di caratteri Unicode](https://docs.microsoft.com/en-us/typography/opentype/spec/os2#ur) campi e non dalla presenza effettiva dei glifi. Anche gli intervalli Unicode vengono controllati individualmente e diversi intervalli relativi a una singola lingua/script possono utilizzare diversi caratteri di fallback.

### Esempi

Mostra come distribuire i caratteri di fallback tra gli intervalli di codice dei caratteri Unicode.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// Configura le nostre impostazioni dei caratteri per i caratteri di origine solo dalla cartella "MyFonts".
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// Chiamare il metodo "BuildAutomatic" genererà uno schema di fallback che
// distribuisce i caratteri accessibili sul maggior numero possibile di codici di caratteri Unicode.
// Nel nostro caso, ha accesso solo alla manciata di caratteri all'interno della cartella "MyFonts".
fontFallbackSettings.BuildAutomatic();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.BuildAutomatic.xml");

// Possiamo anche caricare uno schema di sostituzione personalizzato da un file come questo.
// Questo schema applica il carattere "AllegroOpen" ai blocchi Unicode "0000-00ff", il carattere "AllegroOpen" a "0100-024f",
// e il carattere "M+ 2m" in tutti gli altri intervalli non coperti dagli altri caratteri nello schema.
fontFallbackSettings.Load(MyDir + "Custom font fallback settings.xml");

// Crea un generatore di documenti e imposta il suo carattere su uno che non esiste in nessuna delle nostre fonti.
// Le nostre impostazioni dei caratteri invocheranno lo schema di fallback per i caratteri che digitiamo utilizzando il carattere non disponibile.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Missing Font";

// Usa il builder per stampare ogni carattere Unicode da 0x0021 a 0x052F,
// con linee descrittive che dividono i blocchi Unicode che abbiamo definito nel nostro schema di fallback dei caratteri personalizzato.
for (int i = 0x0021; i < 0x0530; i++)
{
    switch (i)
    {
        case 0x0021:
            builder.Writeln(
                "\n\n0x0021 - 0x00FF: \nBasic Latin/Latin-1 Supplement Unicode blocks in \"AllegroOpen\" font:");
            break;
        case 0x0100:
            builder.Writeln(
                "\n\n0x0100 - 0x024F: \nLatin Extended A/B blocks, mostly in \"AllegroOpen\" font:");
            break;
        case 0x0250:
            builder.Writeln("\n\n0x0250 - 0x052F: \nIPA/Greek/Cyrillic blocks in \"M+ 2m\" font:");
            break;
    }

    builder.Write($"{Convert.ToChar(i)}");
}

doc.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.pdf");
```

### Guarda anche

* class [FontFallbackSettings](../)
* spazio dei nomi [Aspose.Words.Fonts](../../fontfallbacksettings/)
* assemblea [Aspose.Words](../../../)


