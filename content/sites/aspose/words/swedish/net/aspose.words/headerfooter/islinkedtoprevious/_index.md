---
title: HeaderFooter.IsLinkedToPrevious
second_title: Aspose.Words för .NET API Referens
description: HeaderFooter fast egendom. Sant om denna sidhuvud eller sidfot är länkad till motsvarande sidhuvud eller sidfot i föregående avsnitt.
type: docs
weight: 40
url: /sv/net/aspose.words/headerfooter/islinkedtoprevious/
---
## HeaderFooter.IsLinkedToPrevious property

Sant om denna sidhuvud eller sidfot är länkad till motsvarande sidhuvud eller sidfot i föregående avsnitt.

```csharp
public bool IsLinkedToPrevious { get; set; }
```

### Anmärkningar

Standard är sant.

Observera att när du länkar en sidhuvud eller sidfot rensas dess innehåll.

### Exempel

Visar hur du länkar sidhuvuden och sidfötter mellan avsnitt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 3");

// Flytta till det första avsnittet och skapa ett sidhuvud och en sidfot. Som standard,
// sidhuvudet och sidfoten kommer bara att visas på sidorna i avsnittet som innehåller dem.
builder.MoveToSection(0);

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("This is the header, which will be displayed in sections 1 and 2.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("This is the footer, which will be displayed in sections 1, 2 and 3.");

// Vi kan länka ett avsnitts sidhuvuden/sidfötter till föregående avsnitts sidhuvuden/sidfötter
// för att tillåta länkningssektionen att visa den länkade sektionens sidhuvuden/sidfötter.
doc.Sections[1].HeadersFooters.LinkToPrevious(true);

// Varje sektion kommer fortfarande att ha sina egna sidhuvuds-/sidfotsobjekt. När vi länkar avsnitt,
// länksektionen kommer att visa den länkade sektionens sidhuvud/sidfötter samtidigt som den behåller sin egen.
Assert.AreNotEqual(doc.Sections[0].HeadersFooters[0], doc.Sections[1].HeadersFooters[0]);
Assert.AreNotEqual(doc.Sections[0].HeadersFooters[0].ParentSection, doc.Sections[1].HeadersFooters[0].ParentSection);

// Länka sidhuvuden/sidfötter i det tredje avsnittet till sidhuvuden/sidfötter i det andra avsnittet.
// Det andra avsnittet länkar redan till det första avsnittets sidhuvud/sidfötter,
// så att länka till den andra sektionen skapar en länkkedja.
// Den första, andra och nu tredje sektionen kommer alla att visa den första sektionens rubriker.
doc.Sections[2].HeadersFooters.LinkToPrevious(true);

// Vi kan ta bort länken till ett tidigare avsnitts sidhuvud/sidfötter genom att skicka "false" när vi anropar LinkToPrevious-metoden.
doc.Sections[2].HeadersFooters.LinkToPrevious(false);

// Vi kan också välja endast en specifik typ av sidhuvud/sidfot att länka med den här metoden.
// Det tredje avsnittet kommer nu att ha samma sidfot som det andra och första avsnittet, men inte sidhuvudet.
doc.Sections[2].HeadersFooters.LinkToPrevious(HeaderFooterType.FooterPrimary, true);

// Det första avsnittets sidhuvud/sidfot kan inte länka sig till någonting eftersom det inte finns något tidigare avsnitt.
Assert.AreEqual(2, doc.Sections[0].HeadersFooters.Count);
Assert.AreEqual(2, doc.Sections[0].HeadersFooters.Count(hf => !((HeaderFooter)hf).IsLinkedToPrevious));

// Alla det andra avsnittets sidhuvud/sidfötter är länkade till det första avsnittets sidhuvuden/sidfötter.
Assert.AreEqual(6, doc.Sections[1].HeadersFooters.Count);
Assert.AreEqual(6, doc.Sections[1].HeadersFooters.Count(hf => ((HeaderFooter)hf).IsLinkedToPrevious));

// I den tredje sektionen är endast sidfoten länkad till den första sektionens sidfot via den andra sektionen.
Assert.AreEqual(6, doc.Sections[2].HeadersFooters.Count);
Assert.AreEqual(5, doc.Sections[2].HeadersFooters.Count(hf => !((HeaderFooter)hf).IsLinkedToPrevious));
Assert.True(doc.Sections[2].HeadersFooters[3].IsLinkedToPrevious);

doc.Save(ArtifactsDir + "HeaderFooter.Link.docx");
```

### Se även

* class [HeaderFooter](../)
* namnutrymme [Aspose.Words](../../headerfooter/)
* hopsättning [Aspose.Words](../../../)


