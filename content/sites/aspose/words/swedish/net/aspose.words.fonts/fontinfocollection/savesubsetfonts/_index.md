---
title: FontInfoCollection.SaveSubsetFonts
second_title: Aspose.Words för .NET API Referens
description: FontInfoCollection fast egendom. Anger om en delmängd av de inbäddade TrueTypeteckensnitten ska sparas eller inte med dokumentet. Standardvärdet för den här egenskapen är falsk.
type: docs
weight: 50
url: /sv/net/aspose.words.fonts/fontinfocollection/savesubsetfonts/
---
## FontInfoCollection.SaveSubsetFonts property

Anger om en delmängd av de inbäddade TrueType-teckensnitten ska sparas eller inte med dokumentet. Standardvärdet för den här egenskapen är **falsk**.

Det här alternativet fungerar endast när[`EmbedTrueTypeFonts`](../embedtruetypefonts/) egenskapen är inställd på **Sann**.

```csharp
public bool SaveSubsetFonts { get; set; }
```

### Anmärkningar

Det här alternativet fungerar endast för DOC-, DOCX- och RTF-format.

### Exempel

Visar hur man sparar ett dokument med inbäddade TrueType-teckensnitt.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### Se även

* class [FontInfoCollection](../)
* namnutrymme [Aspose.Words.Fonts](../../fontinfocollection/)
* hopsättning [Aspose.Words](../../../)


