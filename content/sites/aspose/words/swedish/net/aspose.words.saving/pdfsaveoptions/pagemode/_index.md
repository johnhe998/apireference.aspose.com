---
title: PdfSaveOptions.PageMode
second_title: Aspose.Words för .NET API Referens
description: PdfSaveOptions fast egendom. Anger hur PDFdokumentet ska visas när det öppnas i PDFläsaren.
type: docs
weight: 220
url: /sv/net/aspose.words.saving/pdfsaveoptions/pagemode/
---
## PdfSaveOptions.PageMode property

Anger hur PDF-dokumentet ska visas när det öppnas i PDF-läsaren.

```csharp
public PdfPageMode PageMode { get; set; }
```

### Anmärkningar

Standardvärdet ärUseOutlines .

### Exempel

Visar hur du ställer in instruktioner för vissa PDF-läsare att följa när du öppnar ett utdatadokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Ställ in egenskapen "PageMode" till "PdfPageMode.FullScreen" för att få PDF-läsaren att öppna den sparade
// dokument i helskärmsläge, som tar över bildskärmens visning och har inga kontroller synliga.
// Ställ in egenskapen "PageMode" till "PdfPageMode.UseThumbs" för att få PDF-läsaren att visa en separat panel
// med en miniatyrbild för varje sida i dokumentet.
// Ställ in egenskapen "PageMode" till "PdfPageMode.UseOC" för att få PDF-läsaren att visa en separat panel
// som låter oss arbeta med alla lager som finns i dokumentet.
// Ställ in egenskapen "PageMode" till "PdfPageMode.UseOutlines" för att hämta PDF-läsaren
// även för att visa konturen, om möjligt.
// Ställ in egenskapen "PageMode" till "PdfPageMode.UseNone" för att få PDF-läsaren att bara visa själva dokumentet.
// Ställ in egenskapen "PageMode" till "PdfPageMode.UseAttachments" för att göra bilagapanelen synlig.
options.PageMode = pageMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.PageMode.pdf", options);
```

Visar att bearbeta bokmärken i sidhuvuden/sidfötter i ett dokument som vi renderar till PDF.

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Ställ in "PageMode"-egenskapen till "PdfPageMode.UseOutlines" för att visa konturnavigeringsfönstret i utdata-PDF-filen.
saveOptions.PageMode = PdfPageMode.UseOutlines;

// Ställ in egenskapen "DefaultBookmarksOutlineLevel" till "1" för att visa alla
// bokmärken på den första nivån av konturen i utdata-PDF.
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// Ställ in egenskapen "HeaderFooterBookmarksExportMode" till "HeaderFooterBookmarksExportMode.None" till
// exportera inte några bokmärken som finns i sidhuvuden/sidfötter.
// Ställ in egenskapen "HeaderFooterBookmarksExportMode" till "HeaderFooterBookmarksExportMode.First" till
// exportera endast bokmärken i det första avsnittets sidhuvud/sidfötter.
// Ställ in egenskapen "HeaderFooterBookmarksExportMode" till "HeaderFooterBookmarksExportMode.All" till
// exportera bokmärken som finns i alla sidhuvuden/sidfötter.
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### Se även

* enum [PdfPageMode](../../pdfpagemode/)
* class [PdfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pdfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


