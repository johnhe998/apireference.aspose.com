---
title: OutlineOptions.CreateOutlinesForHeadingsInTables
second_title: Aspose.Words för .NET API Referens
description: OutlineOptions fast egendom. Anger om konturer ska skapas för rubriker stycken formaterade med rubrikstilar i tabeller.
type: docs
weight: 40
url: /sv/net/aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/
---
## OutlineOptions.CreateOutlinesForHeadingsInTables property

Anger om konturer ska skapas för rubriker (stycken formaterade med rubrikstilar) i tabeller.

```csharp
public bool CreateOutlinesForHeadingsInTables { get; set; }
```

### Anmärkningar

Standardvärdet är **falsk**.

### Exempel

Visar hur man skapar konturposter för PDF-dokument för rubriker i tabeller.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en tabell med tre rader. Första raden,
// vars text vi kommer att formatera i en rubrikstil, kommer att fungera som kolumnrubrik.
builder.StartTable();
builder.InsertCell();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("Customers");
builder.EndRow();
builder.InsertCell();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Normal;
builder.Write("John Doe");
builder.EndRow();
builder.InsertCell();
builder.Write("Jane Doe");
builder.EndTable();

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Det utgående PDF-dokumentet kommer att innehålla en disposition, som är en innehållsförteckning som listar rubriker i dokumentets brödtext.
// Genom att klicka på en post i denna disposition kommer vi till platsen för dess respektive rubrik.
// Sätt egenskapen "HeadingsOutlineLevels" till "1" för att få dispositionen
// att endast registrera rubriker med rubriknivåer som inte är större än 1.
pdfSaveOptions.OutlineOptions.HeadingsOutlineLevels = 1;

// Ställ in egenskapen "CreateOutlinesForHeadingsInTables" till "false" för att utesluta alla rubriker i tabeller,
// som den vi har skapat ovan från dispositionen.
// Ställ in egenskapen "CreateOutlinesForHeadingsInTables" till "true" för att inkludera alla rubriker i tabeller
// i dispositionen, förutsatt att de har en rubriknivå som inte är större än värdet för egenskapen "HeadingsOutlineLevels".
pdfSaveOptions.OutlineOptions.CreateOutlinesForHeadingsInTables = createOutlinesForHeadingsInTables;

doc.Save(ArtifactsDir + "PdfSaveOptions.TableHeadingOutlines.pdf", pdfSaveOptions);
```

### Se även

* class [OutlineOptions](../)
* namnutrymme [Aspose.Words.Saving](../../outlineoptions/)
* hopsättning [Aspose.Words](../../../)


