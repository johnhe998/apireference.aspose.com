---
title: Section.ClearHeadersFooters
second_title: Aspose.Words för .NET API Referens
description: Section metod. Rensar sidhuvuden och sidfötter i det här avsnittet.
type: docs
weight: 100
url: /sv/net/aspose.words/section/clearheadersfooters/
---
## Section.ClearHeadersFooters method

Rensar sidhuvuden och sidfötter i det här avsnittet.

```csharp
public void ClearHeadersFooters()
```

### Anmärkningar

Texten i alla sidhuvuden och sidfötter rensas, men[`HeaderFooter`](../../headerfooter/) själva föremålen tas inte bort.

Detta gör sidhuvuden och sidfötter i det här avsnittet länkade till sidhuvuden och sidfötter i föregående avsnitt.

### Exempel

Visar hur du rensar innehållet i alla sidhuvuden och sidfötter i ett avsnitt.

```csharp
Document doc = new Document();

Assert.AreEqual(0, doc.FirstSection.HeadersFooters.Count);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("This is the primary header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("This is the primary footer.");

Assert.AreEqual(2, doc.FirstSection.HeadersFooters.Count);

Assert.AreEqual("This is the primary header.", doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetText().Trim());
Assert.AreEqual("This is the primary footer.", doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetText().Trim());

// Töm alla sidhuvuden och sidfötter i det här avsnittet på allt deras innehåll.
// Själva sidhuvuden och sidfötter kommer fortfarande att finnas kvar men har inget att visa.
doc.FirstSection.ClearHeadersFooters();

Assert.AreEqual(2, doc.FirstSection.HeadersFooters.Count);

Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetText().Trim());
Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetText().Trim());
```

### Se även

* class [Section](../)
* namnutrymme [Aspose.Words](../../section/)
* hopsättning [Aspose.Words](../../../)


