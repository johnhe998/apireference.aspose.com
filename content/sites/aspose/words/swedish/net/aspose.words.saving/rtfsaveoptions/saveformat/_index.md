---
title: RtfSaveOptions.SaveFormat
second_title: Aspose.Words för .NET API Referens
description: RtfSaveOptions fast egendom. Anger formatet som dokumentet kommer att sparas i om detta sparaalternativobjekt används. Kan endastRtf .
type: docs
weight: 40
url: /sv/net/aspose.words.saving/rtfsaveoptions/saveformat/
---
## RtfSaveOptions.SaveFormat property

Anger formatet som dokumentet kommer att sparas i om detta sparaalternativ-objekt används. Kan endastRtf .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Exempel

Visar hur man sparar ett dokument till .rtf med anpassade alternativ.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Skapa ett "RtfSaveOptions"-objekt för att skicka till dokumentets "Save"-metod för att ändra hur vi sparar det till en RTF.
RtfSaveOptions options = new RtfSaveOptions();

Assert.AreEqual(SaveFormat.Rtf, options.SaveFormat);

// Ställ in egenskapen "ExportCompactSize" till "true" till
// minska storleken på det sparade dokumentet på bekostnad av höger-till-vänster-textkompatibilitet.
options.ExportCompactSize = true;

// Ställ in egenskapen "ExportImagesFotOldReaders" till "true" för att använda extra nyckelord för att säkerställa att vårt dokument är
// kompatibel med pre-Microsoft Word 97 läsare och WordPad.
// Ställ in egenskapen "ExportImagesFotOldReaders" till "false" för att minska storleken på dokumentet,
// men hindra gamla läsare från att kunna läsa eventuella icke-metafiler eller BMP-bilder som dokumentet kan innehålla.
options.ExportImagesForOldReaders = exportImagesForOldReaders;

doc.Save(ArtifactsDir + "RtfSaveOptions.ExportImages.rtf", options);
```

### Se även

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [RtfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../rtfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


