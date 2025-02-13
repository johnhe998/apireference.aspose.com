---
title: PdfSaveOptions.TextCompression
second_title: Aspose.Words för .NET API Referens
description: PdfSaveOptions fast egendom. Anger komprimeringstyp som ska användas för allt textinnehåll i dokumentet.
type: docs
weight: 260
url: /sv/net/aspose.words.saving/pdfsaveoptions/textcompression/
---
## PdfSaveOptions.TextCompression property

Anger komprimeringstyp som ska användas för allt textinnehåll i dokumentet.

```csharp
public PdfTextCompression TextCompression { get; set; }
```

### Anmärkningar

Standard ärFlate.

Ökar utmatningsstorleken avsevärt när du sparar ett dokument utan komprimering.

### Exempel

Visar hur du använder textkomprimering när du sparar ett dokument till PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

for (int i = 0; i < 100; i++)
    builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                    "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Ställ in egenskapen "TextCompression" till "PdfTextCompression.None" för att inte tillämpa någon
// komprimering till text när vi sparar dokumentet till PDF.
// Ställ in egenskapen "TextCompression" till "PdfTextCompression.Flate" för att tillämpa ZIP-komprimering
// till text när vi sparar dokumentet till PDF. Ju större dokument, desto större inverkan kommer detta att ha.
options.TextCompression = pdfTextCompression;

doc.Save(ArtifactsDir + "PdfSaveOptions.TextCompression.pdf", options);
```

### Se även

* enum [PdfTextCompression](../../pdftextcompression/)
* class [PdfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pdfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


