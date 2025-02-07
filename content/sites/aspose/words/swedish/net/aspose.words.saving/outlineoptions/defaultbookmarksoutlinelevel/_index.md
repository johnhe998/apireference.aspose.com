---
title: OutlineOptions.DefaultBookmarksOutlineLevel
second_title: Aspose.Words för .NET API Referens
description: OutlineOptions fast egendom. Anger standardnivån i dokumentkonturen där Wordbokmärken ska visas.
type: docs
weight: 50
url: /sv/net/aspose.words.saving/outlineoptions/defaultbookmarksoutlinelevel/
---
## OutlineOptions.DefaultBookmarksOutlineLevel property

Anger standardnivån i dokumentkonturen där Word-bokmärken ska visas.

```csharp
public int DefaultBookmarksOutlineLevel { get; set; }
```

### Anmärkningar

Individuell bokmärkesnivå kan specificeras med hjälp av[`BookmarksOutlineLevels`](../bookmarksoutlinelevels/) fast egendom.

Ange 0 och Word-bokmärken kommer inte att visas i dokumentkonturen. Ange 1 och Word-bokmärken kommer att visas i dokumentkonturen på nivå 1; 2 för nivå 2 och så vidare.

Standard är 0. Giltigt intervall är 0 till 9.

### Exempel

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

* class [OutlineOptions](../)
* namnutrymme [Aspose.Words.Saving](../../outlineoptions/)
* hopsättning [Aspose.Words](../../../)


