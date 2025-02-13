---
title: RtfSaveOptions.ExportCompactSize
second_title: Aspose.Words för .NET API Referens
description: RtfSaveOptions fast egendom. Gör det möjligt att göra utmatade RTFdokument mindre i storlek men om de innehåller RTL högertillvänster text kommer den inte att visas korrekt. Standardvärdet ärfalsk .
type: docs
weight: 20
url: /sv/net/aspose.words.saving/rtfsaveoptions/exportcompactsize/
---
## RtfSaveOptions.ExportCompactSize property

Gör det möjligt att göra utmatade RTF-dokument mindre i storlek, men om de innehåller RTL (höger-till-vänster) text kommer den inte att visas korrekt. Standardvärdet är`falsk` .

```csharp
public bool ExportCompactSize { get; set; }
```

### Anmärkningar

Om dokumentet som du vill konvertera till RTF med Aspose.Words inte innehåller höger-till-vänster text på språk som arabiska, kan du ställa in det här alternativet till`Sann` för att minska storleken på den resulterande RTF:n.

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

* class [RtfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../rtfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


