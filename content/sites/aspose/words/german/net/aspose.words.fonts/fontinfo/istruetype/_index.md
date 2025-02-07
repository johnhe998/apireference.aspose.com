---
title: FontInfo.IsTrueType
second_title: Aspose.Words für .NET-API-Referenz
description: FontInfo eigendom. Gibt an dass es sich bei dieser Schriftart um eine TrueType oder OpenTypeSchrift handelt und nicht um eine Raster oder Vektorschrift. Die Standardeinstellung ist true.
type: docs
weight: 40
url: /de/net/aspose.words.fonts/fontinfo/istruetype/
---
## FontInfo.IsTrueType property

Gibt an, dass es sich bei dieser Schriftart um eine TrueType- oder OpenType-Schrift handelt und nicht um eine Raster- oder Vektorschrift. Die Standardeinstellung ist „true“.

```csharp
public bool IsTrueType { get; set; }
```

### Beispiele

Zeigt, wie die Details zu den in einem Dokument vorhandenen Schriftarten gedruckt werden.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Drucken Sie alle verwendeten und nicht verwendeten Schriftarten im Dokument.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

### Siehe auch

* class [FontInfo](../)
* namensraum [Aspose.Words.Fonts](../../fontinfo/)
* Montage [Aspose.Words](../../../)


