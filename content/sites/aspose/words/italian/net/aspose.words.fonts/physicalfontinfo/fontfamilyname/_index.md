---
title: PhysicalFontInfo.FontFamilyName
second_title: Aspose.Words per .NET API Reference
description: PhysicalFontInfo proprietà. Cognome del font.
type: docs
weight: 20
url: /it/net/aspose.words.fonts/physicalfontinfo/fontfamilyname/
---
## PhysicalFontInfo.FontFamilyName property

Cognome del font.

```csharp
public string FontFamilyName { get; }
```

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

* class [PhysicalFontInfo](../)
* spazio dei nomi [Aspose.Words.Fonts](../../physicalfontinfo/)
* assemblea [Aspose.Words](../../../)


