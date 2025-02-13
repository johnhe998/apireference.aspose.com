---
title: Section.ClearHeadersFooters
second_title: Aspose.Words für .NET-API-Referenz
description: Section methode. Löscht die Kopf und Fußzeilen dieses Abschnitts.
type: docs
weight: 100
url: /de/net/aspose.words/section/clearheadersfooters/
---
## Section.ClearHeadersFooters method

Löscht die Kopf- und Fußzeilen dieses Abschnitts.

```csharp
public void ClearHeadersFooters()
```

### Bemerkungen

Der Text aller Kopf- und Fußzeilen wird gelöscht, aber[`HeaderFooter`](../../headerfooter/) Objekte selbst werden nicht entfernt.

Dadurch werden Kopf- und Fußzeilen dieses Abschnitts mit Kopf- und Fußzeilen des vorherigen Abschnitts verknüpft.

### Beispiele

Zeigt, wie der Inhalt aller Kopf- und Fußzeilen in einem Abschnitt gelöscht wird.

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

// Leeren Sie alle Kopf- und Fußzeilen in diesem Abschnitt von ihrem gesamten Inhalt.
// Die Kopf- und Fußzeilen selbst sind noch vorhanden, haben aber nichts anzuzeigen.
doc.FirstSection.ClearHeadersFooters();

Assert.AreEqual(2, doc.FirstSection.HeadersFooters.Count);

Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetText().Trim());
Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetText().Trim());
```

### Siehe auch

* class [Section](../)
* namensraum [Aspose.Words](../../section/)
* Montage [Aspose.Words](../../../)


