---
title: PageSetup.FootnoteOptions
second_title: Aspose.Words för .NET API Referens
description: PageSetup fast egendom. Ger alternativ som styr numrering och placering av fotnoter i det här avsnittet.
type: docs
weight: 150
url: /sv/net/aspose.words/pagesetup/footnoteoptions/
---
## PageSetup.FootnoteOptions property

Ger alternativ som styr numrering och placering av fotnoter i det här avsnittet.

```csharp
public FootnoteOptions FootnoteOptions { get; }
```

### Exempel

Visar hur man konfigurerar alternativ som påverkar fotnoter/slutnoter i ett avsnitt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote reference text.");

// Konfigurera alla fotnoter i det första avsnittet för att starta om numreringen från 1
// på varje ny sida och visa sig direkt under texten på varje sida.
FootnoteOptions footnoteOptions = doc.Sections[0].PageSetup.FootnoteOptions;
footnoteOptions.Position = FootnotePosition.BeneathText;
footnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
footnoteOptions.StartNumber = 1;

builder.Write(" Hello again.");
builder.InsertFootnote(FootnoteType.Footnote, "Endnote reference text.");

// Konfigurera alla slutnoter i det första avsnittet för att upprätthålla en kontinuerlig räkning genom hela avsnittet,
// med början från 1. Ställ också in alla så att de visas samlade i slutet av dokumentet.
EndnoteOptions endnoteOptions = doc.Sections[0].PageSetup.EndnoteOptions;
endnoteOptions.Position = EndnotePosition.EndOfDocument;
endnoteOptions.RestartRule = FootnoteNumberingRule.Continuous;
endnoteOptions.StartNumber = 1;

doc.Save(ArtifactsDir + "PageSetup.FootnoteOptions.docx");
```

### Se även

* class [FootnoteOptions](../../../aspose.words.notes/footnoteoptions/)
* class [PageSetup](../)
* namnutrymme [Aspose.Words](../../pagesetup/)
* hopsättning [Aspose.Words](../../../)


