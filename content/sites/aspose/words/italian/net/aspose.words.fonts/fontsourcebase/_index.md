---
title: Class FontSourceBase
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fonts.FontSourceBase classe. Questa è una classe base astratta per le classi che consentono allutente di specificare varie fonti di font.
type: docs
weight: 2800
url: /it/net/aspose.words.fonts/fontsourcebase/
---
## FontSourceBase class

Questa è una classe base astratta per le classi che consentono all'utente di specificare varie fonti di font.

```csharp
public abstract class FontSourceBase
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Restituisce la priorità dell'origine del carattere. |
| abstract [Type](../../aspose.words.fonts/fontsourcebase/type/) { get; } | Restituisce il tipo di origine del carattere. |
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

* spazio dei nomi [Aspose.Words.Fonts](../../aspose.words.fonts/)
* assemblea [Aspose.Words](../../)


