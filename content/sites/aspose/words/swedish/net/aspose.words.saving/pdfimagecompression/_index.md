---
title: Enum PdfImageCompression
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.PdfImageCompression uppräkning. Anger vilken typ av komprimering som tillämpas på bilder i PDFfilen.
type: docs
weight: 5210
url: /sv/net/aspose.words.saving/pdfimagecompression/
---
## PdfImageCompression enumeration

Anger vilken typ av komprimering som tillämpas på bilder i PDF-filen.

```csharp
public enum PdfImageCompression
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Auto | `0` | Väljer automatiskt den lämpligaste komprimeringen för varje bild. |
| Jpeg | `1` | Jpeg-komprimering. Stöder inte transparens. |

### Exempel

Visar hur man anger en komprimeringstyp för alla bilder i ett dokument som vi konverterar till PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Ställ in egenskapen "ImageCompression" till "PdfImageCompression.Auto" för att använda
// Egenskapen "ImageCompression" för att kontrollera kvaliteten på Jpeg-bilderna som hamnar i utdata-PDF.
// Ställ in egenskapen "ImageCompression" till "PdfImageCompression.Jpeg" för att använda
// Egenskapen "ImageCompression" för att kontrollera kvaliteten på alla bilder som hamnar i utdata-PDF.
pdfSaveOptions.ImageCompression = pdfImageCompression;

// Ställ in egenskapen "JpegQuality" till "10" för att stärka komprimeringen till priset av bildkvalitet.
pdfSaveOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageCompression.pdf", pdfSaveOptions);
```

### Se även

* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


