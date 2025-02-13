---
title: Class MemoryFontSource
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fonts.MemoryFontSource classe. Rappresenta il singolo file di font TrueType archiviato in memoria.
type: docs
weight: 2840
url: /it/net/aspose.words.fonts/memoryfontsource/
---
## MemoryFontSource class

Rappresenta il singolo file di font TrueType archiviato in memoria.

```csharp
public class MemoryFontSource : FontSourceBase
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [MemoryFontSource](memoryfontsource/#constructor)(byte[]) | Tor. |
| [MemoryFontSource](memoryfontsource/#constructor_1)(byte[], int) | Tor. |
| [MemoryFontSource](memoryfontsource/#constructor_2)(byte[], int, string) | Tor. |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/memoryfontsource/cachekey/) { get; } | La chiave di questa sorgente nella cache. |
| [FontData](../../aspose.words.fonts/memoryfontsource/fontdata/) { get; } | Dati font binari. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Restituisce la priorità dell'origine del carattere. |
| override [Type](../../aspose.words.fonts/memoryfontsource/type/) { get; } | Restituisce il tipo di origine del carattere. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Chiamato durante l'elaborazione dell'origine del carattere quando viene rilevato un problema che potrebbe causare una perdita di fedeltà di formattazione. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Restituisce l'elenco dei caratteri disponibili tramite questa fonte. |

### Esempi

Mostra come utilizzare una matrice di byte con i dati di un file di font come origine di font.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Guarda anche

* class [FontSourceBase](../fontsourcebase/)
* spazio dei nomi [Aspose.Words.Fonts](../../aspose.words.fonts/)
* assemblea [Aspose.Words](../../)


