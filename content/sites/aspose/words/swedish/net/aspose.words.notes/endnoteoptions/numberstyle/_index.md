---
title: EndnoteOptions.NumberStyle
second_title: Aspose.Words för .NET API Referens
description: EndnoteOptions fast egendom. Anger nummerformatet för automatiskt numrerade slutnoter.
type: docs
weight: 10
url: /sv/net/aspose.words.notes/endnoteoptions/numberstyle/
---
## EndnoteOptions.NumberStyle property

Anger nummerformatet för automatiskt numrerade slutnoter.

```csharp
public NumberStyle NumberStyle { get; set; }
```

### Anmärkningar

Alla nummerstilar är inte tillämpliga för den här egenskapen. För listan över tillämpliga talstilar, se dialogrutan Infoga fotnot eller slutnot i Microsoft Word. Om du väljer en talstil som inte är tillämplig, kommer Microsoft Word att återgå till ett standardvärde.

### Exempel

Visar hur man ändrar nummerstilen för fotnots-/slutnotsreferensmärken.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fotnoter och slutnoter är ett sätt att bifoga en referens eller en sidokommentar till text
// som inte stör flödet i huvudtexten. 
// Att infoga en fotnot/slutnot lägger till en liten upphöjd referenssymbol
// vid huvudtexten där vi infogar fotnoten/slutnoten.
// Varje fotnot/slutnot skapar också en post, som består av en symbol som matchar referensen
// symbol i huvudtexten. Referenstexten som vi skickar till dokumentbyggarens "InsertEndnote"-metod.
// Fotnotsposter visas som standard längst ner på varje sida som innehåller
// deras referenssymboler och slutnoter visas i slutet av dokumentet.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.", "Custom footnote reference mark");

builder.InsertParagraph();

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.", "Custom endnote reference mark");

// Som standard är referenssymbolen för varje fotnot och slutnot dess index
// bland alla dokumentets fotnoter/slutnoter. Varje dokument har separata räkningar
// för fotnoter och för slutnoter. Som standard visar fotnoter deras nummer med arabiska siffror,
// och slutnoter visar sina nummer med gemener romerska siffror.
Assert.AreEqual(NumberStyle.Arabic, doc.FootnoteOptions.NumberStyle);
Assert.AreEqual(NumberStyle.LowercaseRoman, doc.EndnoteOptions.NumberStyle);

// Vi kan använda egenskapen "NumberStyle" för att tillämpa anpassade numreringsstilar på fotnoter och slutnoter.
// Detta kommer inte att påverka fotnoter/slutnoter med anpassade referensmärken.
doc.FootnoteOptions.NumberStyle = NumberStyle.UppercaseRoman;
doc.EndnoteOptions.NumberStyle = NumberStyle.UppercaseLetter;

doc.Save(ArtifactsDir + "InlineStory.RefMarkNumberStyle.docx");
```

### Se även

* enum [NumberStyle](../../../aspose.words/numberstyle/)
* class [EndnoteOptions](../)
* namnutrymme [Aspose.Words.Notes](../../endnoteoptions/)
* hopsättning [Aspose.Words](../../../)


