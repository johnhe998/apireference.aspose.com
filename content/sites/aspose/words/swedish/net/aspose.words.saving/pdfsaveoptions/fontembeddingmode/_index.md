---
title: PdfSaveOptions.FontEmbeddingMode
second_title: Aspose.Words för .NET API Referens
description: PdfSaveOptions fast egendom. Anger typsnittets inbäddningsläge.
type: docs
weight: 140
url: /sv/net/aspose.words.saving/pdfsaveoptions/fontembeddingmode/
---
## PdfSaveOptions.FontEmbeddingMode property

Anger typsnittets inbäddningsläge.

```csharp
public PdfFontEmbeddingMode FontEmbeddingMode { get; set; }
```

### Anmärkningar

Standardvärdet ärEmbedAll.

Den här inställningen fungerar endast för text i ANSI-kodning (Windows-1252). Om dokumentet innehåller icke-ANSI-text kommer motsvarande teckensnitt att bäddas in oavsett denna inställning.

PDF/A- och PDF/UA-kompatibilitet kräver att alla teckensnitt är inbäddade. EmbedAll värde kommer att användas automatiskt när du sparar to PDF/A och PDF/UA.

### Exempel

Visar hur du ställer in Aspose.Words för att hoppa över att bädda in Arial- och Times New Roman-teckensnitt i ett PDF-dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "Arial" är ett standardteckensnitt och "Courier New" är ett icke-standardtypsnitt.
builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Ställ in egenskapen "EmbedFullFonts" till "true" för att bädda in varje glyf för alla inbäddade teckensnitt i den utgående PDF-filen.
options.EmbedFullFonts = true;

// Ställ in egenskapen "FontEmbeddingMode" till "EmbedAll" för att bädda in alla teckensnitt i utdata-PDF-filen.
// Ställ in egenskapen "FontEmbeddingMode" till "EmbedNonstandard" för att endast tillåta icke-standardtypsnitts inbäddning i utdata-PDF.
// Ställ in egenskapen "FontEmbeddingMode" till "EmbedNone" för att inte bädda in några teckensnitt i utdata-PDF-filen.
options.FontEmbeddingMode = pdfFontEmbeddingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf", options);

switch (pdfFontEmbeddingMode)
{
    case PdfFontEmbeddingMode.EmbedAll:
        Assert.That(1000000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNonstandard:
        Assert.That(480000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNone:
        Assert.That(4217, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
}
```

### Se även

* enum [PdfFontEmbeddingMode](../../pdffontembeddingmode/)
* class [PdfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pdfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


