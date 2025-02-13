---
title: HtmlSaveOptions.ExportTocPageNumbers
second_title: Aspose.Words för .NET API Referens
description: HtmlSaveOptions fast egendom. Anger om sidnummer ska skrivas till innehållsförteckningen när HTML MHTML och EPUB sparas. Standardvärdet ärfalsk .
type: docs
weight: 280
url: /sv/net/aspose.words.saving/htmlsaveoptions/exporttocpagenumbers/
---
## HtmlSaveOptions.ExportTocPageNumbers property

Anger om sidnummer ska skrivas till innehållsförteckningen när HTML, MHTML och EPUB sparas. Standardvärdet är`falsk` .

```csharp
public bool ExportTocPageNumbers { get; set; }
```

### Exempel

Visar hur man visar sidnummer när man sparar ett dokument med en innehållsförteckning till .html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en innehållsförteckning och fyll sedan i dokumentet med stycken formaterade med en "Rubrik"
// stil som innehållsförteckningen kommer att plocka upp som poster. Varje post kommer att visa rubrikstycket till vänster,
// och sidnumret som innehåller rubriken till höger.
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 1"];
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 1");
builder.Writeln("Entry 2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 3");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 4");
fieldToc.UpdatePageNumbers();
doc.UpdateFields();

// HTML-dokument har inga sidor. Om vi sparar det här dokumentet i HTML,
// sidnumren som vår innehållsförteckning visar kommer inte att ha någon betydelse.
// När vi sparar dokumentet till HTML kan vi skicka ett SaveOptions-objekt för att utelämna dessa sidnummer från innehållsförteckningen.
// Om vi ställer in "ExportTocPageNumbers"-flaggan till "true",
// varje innehållsförteckningspost kommer att visa rubriken, avgränsaren och sidnumret, och bevara dess utseende i Microsoft Word.
// Om vi ställer in "ExportTocPageNumbers"-flaggan till "false",
// Spara operationen kommer att utelämna både avgränsare och sidnummer och lämnar rubriken för varje post intakt.
HtmlSaveOptions options = new HtmlSaveOptions { ExportTocPageNumbers = exportTocPageNumbers };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportTocPageNumbers.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportTocPageNumbers.html");

if (exportTocPageNumbers)
{
    Assert.True(outDocContents.Contains(
        "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
        "<span>Entry 1</span>" +
        "<span style=\"width:428.14pt; font-family:'Lucida Console'; font-size:10pt; display:inline-block; -aw-font-family:'Times New Roman'; " +
        "-aw-tabstop-align:right; -aw-tabstop-leader:dots; -aw-tabstop-pos:469.8pt\">.......................................................................</span>" +
        "<span>2</span>" +
        "</p>"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
        "<span>Entry 1</span>" +
        "</p>"));
}
```

### Se även

* class [HtmlSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../htmlsaveoptions/)
* hopsättning [Aspose.Words](../../../)


