---
title: Enum EmbeddedFontStyle
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Fonts.EmbeddedFontStyle uppräkning. Anger stilen för ett inbäddat teckensnitt i enFontInfo objekt.
type: docs
weight: 2680
url: /sv/net/aspose.words.fonts/embeddedfontstyle/
---
## EmbeddedFontStyle enumeration

Anger stilen för ett inbäddat teckensnitt i en[`FontInfo`](../fontinfo/) objekt.

```csharp
[Flags]
public enum EmbeddedFontStyle
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Regular | `0` | Anger det vanliga inbäddade teckensnittet. |
| Bold | `1` | Anger det inbäddade teckensnittet med fet stil. |
| Italic | `2` | Anger det inbäddade kursivt teckensnitt. |
| BoldItalic | `3` | Anger det inbäddade teckensnittet med fet kursiv. |

### Exempel

Visar hur man extraherar ett inbäddat teckensnitt från ett dokument och sparar det i det lokala filsystemet.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfo embeddedFont = doc.FontInfos["Alte DIN 1451 Mittelschrift"];
byte[] embeddedFontBytes = embeddedFont.GetEmbeddedFont(EmbeddedFontFormat.OpenType, EmbeddedFontStyle.Regular);
File.WriteAllBytes(ArtifactsDir + "Alte DIN 1451 Mittelschrift.ttf", embeddedFontBytes);

// Inbäddade teckensnittsformat kan vara annorlunda i andra format som .doc.
// Vi behöver veta det korrekta formatet innan vi kan extrahera teckensnittet.
doc = new Document(MyDir + "Embedded font.doc");

Assert.IsNull(doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFont(EmbeddedFontFormat.OpenType, EmbeddedFontStyle.Regular));
Assert.IsNotNull(doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFont(EmbeddedFontFormat.EmbeddedOpenType, EmbeddedFontStyle.Regular));

// Dessutom kan vi konvertera inbäddat OpenType-format, som kommer från .doc-dokument, till OpenType.
embeddedFontBytes = doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFontAsOpenType(EmbeddedFontStyle.Regular);

File.WriteAllBytes(ArtifactsDir + "Alte DIN 1451 Mittelschrift.otf", embeddedFontBytes);
```

### Se även

* namnutrymme [Aspose.Words.Fonts](../../aspose.words.fonts/)
* hopsättning [Aspose.Words](../../)


