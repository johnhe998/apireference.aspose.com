---
title: Enum HtmlElementSizeOutputMode
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.HtmlElementSizeOutputMode uppräkning. Anger hur Aspose.Words exporterar elementbredder och höjder till HTML MHTML och EPUB.
type: docs
weight: 4800
url: /sv/net/aspose.words.saving/htmlelementsizeoutputmode/
---
## HtmlElementSizeOutputMode enumeration

Anger hur Aspose.Words exporterar elementbredder och höjder till HTML, MHTML och EPUB.

```csharp
public enum HtmlElementSizeOutputMode
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| All | `0` | Alla elementstorlekar, både i absoluta och relativa enheter, som anges i dokumentet exporteras. |
| RelativeOnly | `1` | Elementstorlekar exporteras endast om de anges i relativa enheter i dokumentet. Fasta storlekar exporteras inte i detta läge. Visuella agenter kommer att beräkna saknade storlekar för att göra dokumentlayout mer naturlig. |
| None | `2` | Elementstorlekar exporteras inte. Visuella agenter kommer att bygga layout automatiskt enligt förhållandet mellan elementen. |

### Exempel

Visar hur man bevarar negativa indrag i utdata .html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en tabell med ett negativt indrag, vilket kommer att skjuta den till vänster förbi den vänstra sidgränsen.
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, Cell 1");
builder.InsertCell();
builder.Write("Row 1, Cell 2");
builder.EndTable();
table.LeftIndent = -36;
table.PreferredWidth = PreferredWidth.FromPoints(144);

builder.InsertBreak(BreakType.ParagraphBreak);

// Infoga en tabell med ett positivt indrag, vilket kommer att skjuta tabellen åt höger.
table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, Cell 1");
builder.InsertCell();
builder.Write("Row 1, Cell 2");
builder.EndTable();
table.LeftIndent = 36;
table.PreferredWidth = PreferredWidth.FromPoints(144);

// När vi sparar ett dokument till HTML kommer Aspose.Words endast att bevara negativa indrag
// som den vi har tillämpat på den första tabellen om vi ställer in flaggan "AllowNegativeIndent"
// i ett SaveOptions-objekt som vi skickar till "true".
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    AllowNegativeIndent = allowNegativeIndent,
    TableWidthOutputMode = HtmlElementSizeOutputMode.RelativeOnly
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.NegativeIndent.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.NegativeIndent.html");

if (allowNegativeIndent)
{
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:-41.65pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:30.35pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:30.35pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
}
```

### Se även

* property [TableWidthOutputMode](../htmlsaveoptions/tablewidthoutputmode/)
* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


