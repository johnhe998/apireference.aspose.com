---
title: Class FileFontSource
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fonts.FileFontSource classe. Rappresenta il singolo file di font TrueType archiviato nel file system.
type: docs
weight: 2690
url: /it/net/aspose.words.fonts/filefontsource/
---
## FileFontSource class

Rappresenta il singolo file di font TrueType archiviato nel file system.

```csharp
public class FileFontSource : FontSourceBase
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [FileFontSource](filefontsource/#constructor)(string) | Tor. |
| [FileFontSource](filefontsource/#constructor_1)(string, int) | Tor. |
| [FileFontSource](filefontsource/#constructor_2)(string, int, string) | Tor. |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/filefontsource/cachekey/) { get; } | La chiave di questa sorgente nella cache. |
| [FilePath](../../aspose.words.fonts/filefontsource/filepath/) { get; } | Percorso del file del carattere. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Restituisce la priorità dell'origine del carattere. |
| override [Type](../../aspose.words.fonts/filefontsource/type/) { get; } | Restituisce il tipo di origine del carattere. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Chiamato durante l'elaborazione dell'origine del carattere quando viene rilevato un problema che potrebbe causare una perdita di fedeltà di formattazione. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Restituisce l'elenco dei caratteri disponibili tramite questa fonte. |

### Esempi

Mostra come utilizzare un file di font nel file system locale come origine di font.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Guarda anche

* class [FontSourceBase](../fontsourcebase/)
* spazio dei nomi [Aspose.Words.Fonts](../../aspose.words.fonts/)
* assemblea [Aspose.Words](../../)


