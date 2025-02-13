---
title: Enum PdfCompliance
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.PdfCompliance uppräkning. Anger överensstämmelsenivån för PDFstandarder.
type: docs
weight: 5130
url: /sv/net/aspose.words.saving/pdfcompliance/
---
## PdfCompliance enumeration

Anger överensstämmelsenivån för PDF-standarder.

```csharp
public enum PdfCompliance
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Pdf17 | `0` | Utdatafilen kommer att följa standarden PDF 1.7 (ISO 32000-1). |
| Pdf20 | `1` | Utdatafilen kommer att följa standarden PDF 2.0 (ISO 32000-2). |
| PdfA1a | `2` | Utdatafilen kommer att följa standarden PDF/A-1a (ISO 19005-1). Denna nivå inkluderar alla kraven i PDF/A-1b och kräver dessutom att dokumentstrukturen ska inkluderas (även känd som "taggad" ), med målet att säkerställa att dokumentinnehåll kan sökas i och återanvändas. |
| PdfA1b | `3` | Utdatafilen kommer att följa standarden PDF/A-1b (ISO 19005-1). PDF/A-1b har som mål att säkerställa tillförlitlig återgivning av dokumentets visuella utseende. |
| PdfA2a | `4` | Utdatafilen kommer att följa standarden PDF/A-2a (ISO 19005-2). Den här nivån inkluderar alla krav i PDF/A-2u och kräver dessutom att dokumentstrukturen inkluderas (även känd som "taggad" ), med målet att säkerställa att dokumentinnehåll kan sökas i och återanvändas. |
| PdfA2u | `5` | Utdatafilen kommer att följa standarden PDF/A-2u (ISO 19005-2). PDF/A-2u har som mål att bevara dokumentets statiska visuella utseende över tid, oberoende av verktygen och systemen som används för att skapa, lagra eller rendera filerna. Dessutom kan all text som finns i document extraheras tillförlitligt som en serie Unicode-kodpunkter. |
| PdfA4 | `6` | Utdatafilen kommer att följa standarden PDF/A-4 (ISO 19005-4:2020). PDF/A-4 har som mål att bevara dokumentets statiska visuella utseende över tid, oberoende av verktygen och systemen som används för att skapa , lagra eller rendera filerna. Dessutom kan all text som finns i document extraheras tillförlitligt som en serie Unicode-kodpunkter. |
| PdfUa1 | `7` | Utdatafilen kommer att följa standarden PDF/UA-1 (ISO 14289-1). Det primära syftet med PDF/UA är att definiera hur elektroniska dokument ska representeras i PDF-formatet på ett sätt som gör att filen kan tillgänglig. |

### Exempel

Visar hur du ställer in PDF-standardens överensstämmelsenivå för sparade PDF-dokument.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
// Observera att vissa PdfSaveOptions är förbjudna när du sparar till en av standarderna och automatiskt fixade.
// Använd IWarningCallback för att veta vilka alternativ som automatiskt åtgärdas.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Ställ in egenskapen "Compliance" till "PdfCompliance.PdfA1b" för att följa standarden "PDF/A-1b",
// som syftar till att bevara dokumentets visuella utseende när Aspose.Words konverterar det till PDF.
// Ställ in egenskapen "Compliance" till "PdfCompliance.Pdf17" för att följa standarden "1.7".
// Ställ in egenskapen "Compliance" till "PdfCompliance.PdfA1a" för att följa standarden "PDF/A-1a",
// som överensstämmer med "PDF/A-1b" samt bevarar originaldokumentets dokumentstruktur.
// Ställ in egenskapen "Compliance" till "PdfCompliance.PdfUa1" för att följa standarden "PDF/UA-1" (ISO 14289-1),
// som syftar till att definiera representera elektroniska dokument i PDF som gör att filen är tillgänglig.
// Detta hjälper till att göra dokument sökbara men kan avsevärt öka storleken på redan stora dokument.
saveOptions.Compliance = pdfCompliance;

doc.Save(ArtifactsDir + "PdfSaveOptions.Compliance.pdf", saveOptions);
```

### Se även

* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


