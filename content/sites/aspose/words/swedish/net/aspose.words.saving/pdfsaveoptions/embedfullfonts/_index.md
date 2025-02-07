---
title: PdfSaveOptions.EmbedFullFonts
second_title: Aspose.Words för .NET API Referens
description: PdfSaveOptions fast egendom. Styr hur teckensnitt bäddas in i de resulterande PDFdokumenten.
type: docs
weight: 100
url: /sv/net/aspose.words.saving/pdfsaveoptions/embedfullfonts/
---
## PdfSaveOptions.EmbedFullFonts property

Styr hur teckensnitt bäddas in i de resulterande PDF-dokumenten.

```csharp
public bool EmbedFullFonts { get; set; }
```

### Anmärkningar

Standardvärdet är`falsk`, vilket innebär att teckensnitten är underinställda innan de bäddas in. Underinställning är användbar om du vill hålla utdatafilens storlek mindre. Underinställning tar bort all oanvända glyfer från ett teckensnitt.

När detta värde är satt till`Sann`är en komplett teckensnittsfil inbäddad i PDF utan underinställning. Detta kommer att resultera i större utdatafiler, men kan vara ett användbart alternativ när du vill redigera den resulterande PDF-filen senare (t.ex. lägga till mer text).

Vissa teckensnitt är stora (flera megabyte) och inbäddning av dem utan subsetting kommer att resultera i stora utdatadokument.

### Exempel

Visar hur du aktiverar eller inaktiverar underinställningar när du bäddar in teckensnitt samtidigt som ett dokument renderas till PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Arvo";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Konfigurera våra teckensnittskällor för att säkerställa att vi har tillgång till båda teckensnitten i det här dokumentet.
FontSourceBase[] originalFontsSources = FontSettings.DefaultInstance.GetFontsSources();
Aspose.Words.Fonts.FolderFontSource folderFontSource = new Aspose.Words.Fonts.FolderFontSource(FontsDir, true);
FontSettings.DefaultInstance.SetFontsSources(new[] { originalFontsSources[0], folderFontSource });

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(fontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Eftersom vårt dokument innehåller ett anpassat typsnitt kan det vara önskvärt att bädda in i utdatadokumentet.
// Ställ in egenskapen "EmbedFullFonts" till "true" för att bädda in varje glyf för alla inbäddade teckensnitt i den utgående PDF-filen.
// Dokumentets storlek kan bli mycket stor, men vi kommer att ha full användning av alla typsnitt om vi redigerar PDF:en.
// Ställ in egenskapen "EmbedFullFonts" till "false" för att tillämpa underinställning på teckensnitt och spara endast glyferna
// som dokumentet använder. Filen blir betydligt mindre,
// men vi kan behöva tillgång till alla anpassade typsnitt om vi redigerar dokumentet.
options.EmbedFullFonts = embedFullFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf", options);

if (embedFullFonts)
    Assert.That(500000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));
else
    Assert.That(25000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));

// Återställ de ursprungliga teckensnittskällorna.
FontSettings.DefaultInstance.SetFontsSources(originalFontsSources);
```

### Se även

* class [PdfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pdfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


