---
title: Enum ColorMode
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.ColorMode uppräkning. Anger hur färger återges.
type: docs
weight: 4600
url: /sv/net/aspose.words.saving/colormode/
---
## ColorMode enumeration

Anger hur färger återges.

```csharp
public enum ColorMode
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Normal | `0` | Återgivning med omodifierade färger. |
| Grayscale | `1` | Återgivning med färger i en rad grå nyanser från vitt till svart. |

### Exempel

Visar hur du ändrar bildfärg med egenskapen sparalternativ.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
// Ställ in egenskapen "ColorMode" till "Gråskala" för att återge alla bilder från dokumentet i svartvitt.
// Storleken på utdatadokumentet kan vara större med den här inställningen.
// Ställ in egenskapen "ColorMode" till "Normal" för att återge alla bilder i färg.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions { ColorMode = colorMode };

doc.Save(ArtifactsDir + "PdfSaveOptions.ColorRendering.pdf", pdfSaveOptions);
```

### Se även

* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


