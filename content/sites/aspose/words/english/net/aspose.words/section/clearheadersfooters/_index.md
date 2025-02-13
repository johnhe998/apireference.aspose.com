---
title: Section.ClearHeadersFooters
linktitle: ClearHeadersFooters
articleTitle: ClearHeadersFooters
second_title: Aspose.Words for .NET
description: Section ClearHeadersFooters method. Clears the headers and footers of this section in C#.
type: docs
weight: 100
url: /net/aspose.words/section/clearheadersfooters/
---
## Section.ClearHeadersFooters method

Clears the headers and footers of this section.

```csharp
public void ClearHeadersFooters()
```

## Remarks

The text of all headers and footers is cleared, but [`HeaderFooter`](../../headerfooter/) objects themselves are not removed.

This makes headers and footers of this section linked to headers and footers of the previous section.

## Examples

Shows how to clear the contents of all headers and footers in a section.

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

// Empty all the headers and footers in this section of all their contents.
// The headers and footers themselves will still be present but will have nothing to display.
doc.FirstSection.ClearHeadersFooters();

Assert.AreEqual(2, doc.FirstSection.HeadersFooters.Count);

Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetText().Trim());
Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetText().Trim());
```

### See Also

* class [Section](../)
* namespace [Aspose.Words](../../../aspose.words/)
* assembly [Aspose.Words](../../../)
