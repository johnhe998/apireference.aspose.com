---
title: Class PhysicalFontInfo
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fonts.PhysicalFontInfo classe. Specifica le informazioni sul carattere fisico disponibile per il motore di caratteri Aspose.Words.
type: docs
weight: 2850
url: /it/net/aspose.words.fonts/physicalfontinfo/
---
## PhysicalFontInfo class

Specifica le informazioni sul carattere fisico disponibile per il motore di caratteri Aspose.Words.

```csharp
public class PhysicalFontInfo
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [FilePath](../../aspose.words.fonts/physicalfontinfo/filepath/) { get; } | Percorso dell'eventuale file del carattere. |
| [FontFamilyName](../../aspose.words.fonts/physicalfontinfo/fontfamilyname/) { get; } | Cognome del font. |
| [FullFontName](../../aspose.words.fonts/physicalfontinfo/fullfontname/) { get; } | Nome completo del carattere. |
| [Version](../../aspose.words.fonts/physicalfontinfo/version/) { get; } | Stringa di versione del font. |

### Esempi

Mostra come elencare i caratteri disponibili.

```csharp
// Configura Aspose.Words per generare i font da una cartella personalizzata, quindi stampa tutti i font disponibili.
FontSourceBase[] folderFontSource = { new FolderFontSource(FontsDir, true) };

foreach (PhysicalFontInfo fontInfo in folderFontSource[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : {0}", fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : {0}", fontInfo.FullFontName);
    Console.WriteLine("Version  : {0}", fontInfo.Version);
    Console.WriteLine("FilePath : {0}\n", fontInfo.FilePath);
}
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Fonts](../../aspose.words.fonts/)
* assemblea [Aspose.Words](../../)


