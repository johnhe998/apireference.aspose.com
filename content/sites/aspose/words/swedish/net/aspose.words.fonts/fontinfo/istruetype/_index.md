---
title: FontInfo.IsTrueType
second_title: Aspose.Words för .NET API Referens
description: FontInfo fast egendom. Indikerar att detta teckensnitt är ett TrueType eller OpenTypeteckensnitt i motsats till ett raster eller vektorteckensnitt. Standard är true.
type: docs
weight: 40
url: /sv/net/aspose.words.fonts/fontinfo/istruetype/
---
## FontInfo.IsTrueType property

Indikerar att detta teckensnitt är ett TrueType- eller OpenType-teckensnitt i motsats till ett raster- eller vektorteckensnitt. Standard är true.

```csharp
public bool IsTrueType { get; set; }
```

### Exempel

Visar hur man skriver ut information om vilka typsnitt som finns i ett dokument.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Skriv ut alla använda och oanvända typsnitt i dokumentet.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

### Se även

* class [FontInfo](../)
* namnutrymme [Aspose.Words.Fonts](../../fontinfo/)
* hopsättning [Aspose.Words](../../../)


