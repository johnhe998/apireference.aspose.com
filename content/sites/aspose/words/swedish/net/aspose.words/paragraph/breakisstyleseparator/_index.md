---
title: Paragraph.BreakIsStyleSeparator
second_title: Aspose.Words för .NET API Referens
description: Paragraph fast egendom. Sant om denna styckebrytning är en stilavskiljare. En stilavgränsare tillåter one stycke att bestå av delar som har olika styckestilar.
type: docs
weight: 20
url: /sv/net/aspose.words/paragraph/breakisstyleseparator/
---
## Paragraph.BreakIsStyleSeparator property

Sant om denna styckebrytning är en stilavskiljare. En stilavgränsare tillåter one stycke att bestå av delar som har olika styckestilar.

```csharp
public bool BreakIsStyleSeparator { get; }
```

### Exempel

Visar hur man skriver text till samma rad som en innehållsförteckningsrubrik och att den inte visas i innehållsförteckningen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTableOfContents("\\o \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// Infoga ett stycke med en stil som innehållsförteckningen kommer att plocka upp som en post.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

// Båda dessa strängar finns i samma stycke och kommer därför att visas på samma innehållsförteckning.
builder.Write("Heading 1. ");
builder.Write("Will appear in the TOC. ");

// Om vi infogar en stilavgränsare kan vi skriva mer text i samma stycke
// och använd en annan stil utan att dyka upp i innehållsförteckningen.
// Om vi använder en rubrikstil efter avgränsaren kan vi rita flera innehållsförteckningar från en dokumenttextrad.
builder.InsertStyleSeparator();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Quote;
builder.Write("Won't appear in the TOC. ");

Assert.True(doc.FirstSection.Body.FirstParagraph.BreakIsStyleSeparator);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Paragraph.BreakIsStyleSeparator.docx");
```

### Se även

* class [Paragraph](../)
* namnutrymme [Aspose.Words](../../paragraph/)
* hopsättning [Aspose.Words](../../../)


