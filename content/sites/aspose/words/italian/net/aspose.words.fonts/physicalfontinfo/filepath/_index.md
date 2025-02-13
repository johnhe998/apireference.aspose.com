---
title: PhysicalFontInfo.FilePath
second_title: Aspose.Words per .NET API Reference
description: PhysicalFontInfo proprietà. Percorso delleventuale file del carattere.
type: docs
weight: 10
url: /it/net/aspose.words.fonts/physicalfontinfo/filepath/
---
## PhysicalFontInfo.FilePath property

Percorso dell'eventuale file del carattere.

```csharp
public string FilePath { get; }
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


