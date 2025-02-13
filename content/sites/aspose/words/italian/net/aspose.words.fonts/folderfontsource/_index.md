---
title: Class FolderFontSource
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fonts.FolderFontSource classe. Rappresenta la cartella che contiene i file di font TrueType.
type: docs
weight: 2700
url: /it/net/aspose.words.fonts/folderfontsource/
---
## FolderFontSource class

Rappresenta la cartella che contiene i file di font TrueType.

```csharp
public class FolderFontSource : FontSourceBase
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [FolderFontSource](folderfontsource/#constructor)(string, bool) | Tor. |
| [FolderFontSource](folderfontsource/#constructor_1)(string, bool, int) | Tor. |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [FolderPath](../../aspose.words.fonts/folderfontsource/folderpath/) { get; } | Percorso della cartella. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Restituisce la priorità dell'origine del carattere. |
| [ScanSubfolders](../../aspose.words.fonts/folderfontsource/scansubfolders/) { get; } | Determina se scansionare o meno le sottocartelle. |
| override [Type](../../aspose.words.fonts/folderfontsource/type/) { get; } | Restituisce il tipo di origine del carattere. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Chiamato durante l'elaborazione dell'origine del carattere quando viene rilevato un problema che potrebbe causare una perdita di fedeltà di formattazione. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Restituisce l'elenco dei caratteri disponibili tramite questa fonte. |

### Esempi

Mostra come utilizzare una cartella di sistema locale che contiene i caratteri come origine dei caratteri.

```csharp
// Crea una fonte di font da una cartella che contiene file di font.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### Guarda anche

* class [FontSourceBase](../fontsourcebase/)
* spazio dei nomi [Aspose.Words.Fonts](../../aspose.words.fonts/)
* assemblea [Aspose.Words](../../)


