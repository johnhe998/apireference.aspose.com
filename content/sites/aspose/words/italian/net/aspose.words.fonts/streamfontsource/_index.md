---
title: Class StreamFontSource
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fonts.StreamFontSource classe. Classe base per lorigine del font stream definita dallutente.
type: docs
weight: 2860
url: /it/net/aspose.words.fonts/streamfontsource/
---
## StreamFontSource class

Classe base per l'origine del font stream definita dall'utente.

```csharp
public abstract class StreamFontSource : FontSourceBase
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/streamfontsource/cachekey/) { get; } | La chiave di questa sorgente nella cache. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Restituisce la priorità dell'origine del carattere. |
| [Type](../../aspose.words.fonts/streamfontsource/type/) { get; } | Restituisce il tipo di origine del carattere. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Chiamato durante l'elaborazione dell'origine del carattere quando viene rilevato un problema che potrebbe causare una perdita di fedeltà di formattazione. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Restituisce l'elenco dei caratteri disponibili tramite questa fonte. |
| abstract [OpenFontDataStream](../../aspose.words.fonts/streamfontsource/openfontdatastream/)() | Questo metodo dovrebbe aprire il flusso con i dati dei caratteri su richiesta. |

### Osservazioni

Per utilizzare l'origine del font stream è necessario creare una classe derivata da`StreamFontSource` e fornire l'implementazione del[`OpenFontDataStream`](./openfontdatastream/) metodo.

[`OpenFontDataStream`](./openfontdatastream/)il metodo potrebbe essere chiamato più volte. Per la prima volta verrà chiamato quando Aspose.Words esegue la scansione delle fonti di font fornite per ottenere l'elenco dei font disponibili. Successivamente può essere chiamato se il font viene utilizzato nel documento per analizzare i dati del font e incorporare i dati del font in alcuni formati di output.

`StreamFontSource` può essere utile perché permette di caricare i dati del font solo quando è richiesto e di non salvarli in memoria per il[`FontSettings`](../fontsettings/) tutta la vita.

### Esempi

Mostra come caricare i caratteri dallo stream.

```csharp
{
    FontSettings fontSettings = new FontSettings();
    fontSettings.SetFontsSources(new FontSourceBase[] {new StreamFontSourceFile()});

    DocumentBuilder builder = new DocumentBuilder();
    builder.Document.FontSettings = fontSettings;
    builder.Font.Name = "Kreon-Regular";
    builder.Writeln("Test aspose text when saving to PDF.");

    builder.Document.Save(ArtifactsDir + "FontSettings.StreamFontSourceFileRendering.pdf");
}

/// <summary>
/// Carica i dati del font solo quando richiesto invece di salvarli in memoria
/// per l'intera durata dell'oggetto "FontSettings".
/// </summary>
private class StreamFontSourceFile : StreamFontSource
{
    public override Stream OpenFontDataStream()
    {
        return File.OpenRead(FontsDir + "Kreon-Regular.ttf");
    }
}
```

### Guarda anche

* class [FontSourceBase](../fontsourcebase/)
* spazio dei nomi [Aspose.Words.Fonts](../../aspose.words.fonts/)
* assemblea [Aspose.Words](../../)


