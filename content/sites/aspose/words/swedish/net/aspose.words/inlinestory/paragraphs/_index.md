---
title: InlineStory.Paragraphs
second_title: Aspose.Words för .NET API Referens
description: InlineStory fast egendom. Får en samling stycken som är omedelbara barn till berättelsen.
type: docs
weight: 80
url: /sv/net/aspose.words/inlinestory/paragraphs/
---
## InlineStory.Paragraphs property

Får en samling stycken som är omedelbara barn till berättelsen.

```csharp
public ParagraphCollection Paragraphs { get; }
```

### Exempel

Visar hur man lägger till en kommentar till ett stycke.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Hello world!");

Comment comment = new Comment(doc, "John Doe", "JD", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);
builder.MoveTo(comment.AppendChild(new Paragraph(doc)));
builder.Write("Comment text.");

Assert.AreEqual(DateTime.Today, comment.DateTime);

// I Microsoft Word kan vi högerklicka på den här kommentaren i dokumentets brödtext för att redigera den eller svara på den. 
doc.Save(ArtifactsDir + "InlineStory.AddComment.docx");
```

Visar hur man infogar och anpassar fotnoter.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Lägg till text och referera till den med en fotnot. Denna fotnot kommer att placera en liten upphöjd referens
// markera efter texten som den refererar till och skapa en post under huvudtexten längst ner på sidan.
// Denna post kommer att innehålla fotnotens referensmärke och referenstexten,
// som vi kommer att skicka till dokumentbyggarens "InsertFootnote"-metod.
builder.Write("Main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Om den här egenskapen är inställd på "true", är vår fotnots referensmärke
// kommer att vara dess index bland alla avsnittets fotnoter.
// Detta är den första fotnoten, så referensmärket blir "1".
Assert.True(footnote.IsAuto);

// Vi kan flytta dokumentbyggaren inuti fotnoten för att redigera dess referenstext. 
builder.MoveTo(footnote.FirstParagraph);
builder.Write(" More text added by a DocumentBuilder.");
builder.MoveToDocumentEnd();

Assert.AreEqual("\u0002 Footnote text. More text added by a DocumentBuilder.", footnote.GetText().Trim());

builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Vi kan ställa in ett anpassat referensmärke som fotnoten kommer att använda istället för dess indexnummer.
footnote.ReferenceMark = "RefMark";

Assert.False(footnote.IsAuto);

// Ett bokmärke med flaggan "IsAuto" inställd på sant kommer fortfarande att visa sitt verkliga index
// även om tidigare bokmärken visar anpassade referensmärken, så kommer detta bokmärkes referensmärke att vara en "3".
builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

Assert.True(footnote.IsAuto);

doc.Save(ArtifactsDir + "InlineStory.AddFootnote.docx");
```

### Se även

* class [ParagraphCollection](../../paragraphcollection/)
* class [InlineStory](../)
* namnutrymme [Aspose.Words](../../inlinestory/)
* hopsättning [Aspose.Words](../../../)


