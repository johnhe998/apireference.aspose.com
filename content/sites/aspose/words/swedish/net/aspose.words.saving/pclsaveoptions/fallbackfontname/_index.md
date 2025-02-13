---
title: PclSaveOptions.FallbackFontName
second_title: Aspose.Words för .NET API Referens
description: PclSaveOptions fast egendom. Namn på teckensnittet som kommer att användas om inget förväntat teckensnitt hittas i skrivare och inbyggda teckensnittssamlingar.
type: docs
weight: 20
url: /sv/net/aspose.words.saving/pclsaveoptions/fallbackfontname/
---
## PclSaveOptions.FallbackFontName property

Namn på teckensnittet som kommer att användas om inget förväntat teckensnitt hittas i skrivare och inbyggda teckensnittssamlingar.

```csharp
public string FallbackFontName { get; set; }
```

### Anmärkningar

Om ingen reserv hittas genereras en varning och "Arial"-teckensnitt används.

### Exempel

Visar hur man deklarerar ett teckensnitt som en skrivare kommer att tillämpa på tryckt text som ersättning om dess ursprungliga teckensnitt inte är tillgängligt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Non-existent font";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.FallbackFontName = "Times New Roman";

// Detta dokument kommer att instruera skrivaren att tillämpa "Times New Roman" på texten med det saknade teckensnittet.
// Skulle "Times New Roman" inte heller vara tillgängligt, kommer skrivaren att använda typsnittet "Arial".
doc.Save(ArtifactsDir + "PclSaveOptions.SetPrinterFont.pcl", saveOptions);
```

### Se även

* class [PclSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pclsaveoptions/)
* hopsättning [Aspose.Words](../../../)


