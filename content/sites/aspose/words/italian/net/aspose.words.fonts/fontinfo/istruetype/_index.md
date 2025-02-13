---
title: FontInfo.IsTrueType
second_title: Aspose.Words per .NET API Reference
description: FontInfo proprietà. Indica che questo font è un font TrueType o OpenType anziché un font raster o vettoriale. Limpostazione predefinita è true.
type: docs
weight: 40
url: /it/net/aspose.words.fonts/fontinfo/istruetype/
---
## FontInfo.IsTrueType property

Indica che questo font è un font TrueType o OpenType anziché un font raster o vettoriale. L'impostazione predefinita è true.

```csharp
public bool IsTrueType { get; set; }
```

### Esempi

Mostra come stampare i dettagli di quali font sono presenti in un documento.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Stampa tutti i caratteri usati e non utilizzati nel documento.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

### Guarda anche

* class [FontInfo](../)
* spazio dei nomi [Aspose.Words.Fonts](../../fontinfo/)
* assemblea [Aspose.Words](../../../)


