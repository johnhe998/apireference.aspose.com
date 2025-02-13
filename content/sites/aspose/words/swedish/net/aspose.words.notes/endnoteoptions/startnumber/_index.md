---
title: EndnoteOptions.StartNumber
second_title: Aspose.Words för .NET API Referens
description: EndnoteOptions fast egendom. Anger startnumret eller tecknet för de första automatiskt numrerade slutnoterna.
type: docs
weight: 40
url: /sv/net/aspose.words.notes/endnoteoptions/startnumber/
---
## EndnoteOptions.StartNumber property

Anger startnumret eller tecknet för de första automatiskt numrerade slutnoterna.

```csharp
public int StartNumber { get; set; }
```

### Anmärkningar

Denna egenskap har endast effekt när[`RestartRule`](../restartrule/) är inställd på Continuous.

### Exempel

Visar hur man ställer in ett nummer vid vilket dokumentet börjar räkna fotnot/slutnot.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fotnoter och slutnoter är ett sätt att bifoga en referens eller en sidokommentar till text
// som inte stör flödet i huvudtexten. 
// Att infoga en fotnot/slutnot lägger till en liten upphöjd referenssymbol
// vid huvudtexten där vi infogar fotnoten/slutnoten.
// Varje fotnot/slutnot skapar också en post, som består av en symbol
// som matchar referenssymbolen i huvudtexten.
// Referenstexten som vi skickar till dokumentbyggarens "InsertEndnote"-metod.
// Fotnotsposter visas som standard längst ner på varje sida som innehåller
// deras referenssymboler och slutnoter visas i slutet av dokumentet.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");

builder.InsertParagraph();

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");

// Som standard är referenssymbolen för varje fotnot och slutnot dess index
// bland alla dokumentets fotnoter/slutnoter. Varje dokument har separata räkningar
// för fotnoter och för slutnoter, som båda börjar på 1.
Assert.AreEqual(1, doc.FootnoteOptions.StartNumber);
Assert.AreEqual(1, doc.EndnoteOptions.StartNumber);

// Vi kan använda egenskapen "StartNumber" för att få dokumentet till
// börjar räkna en fotnot eller slutnot med ett annat nummer.
doc.EndnoteOptions.NumberStyle = NumberStyle.Arabic;
doc.EndnoteOptions.StartNumber = 50;

doc.Save(ArtifactsDir + "InlineStory.StartNumber.docx");
```

### Se även

* class [EndnoteOptions](../)
* namnutrymme [Aspose.Words.Notes](../../endnoteoptions/)
* hopsättning [Aspose.Words](../../../)


