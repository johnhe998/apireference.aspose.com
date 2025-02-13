---
title: ParagraphFormat.PageBreakBefore
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Wahr wenn vor dem Absatz ein Seitenumbruch erzwungen wird.
type: docs
weight: 250
url: /de/net/aspose.words/paragraphformat/pagebreakbefore/
---
## ParagraphFormat.PageBreakBefore property

Wahr, wenn vor dem Absatz ein Seitenumbruch erzwungen wird.

```csharp
public bool PageBreakBefore { get; set; }
```

### Beispiele

Zeigt, wie Absätze mit Seitenumbrüchen am Anfang erstellt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Setzen Sie dieses Flag auf "true", um einen Seitenumbruch am Anfang jedes Absatzes anzuwenden
// die der Document Builder unter dieser ParagraphFormat-Konfiguration erstellen wird.
// Der erste Absatz erhält keinen Seitenumbruch.
// Lassen Sie dieses Flag auf "false", um jeden neuen Absatz auf derselben Seite zu beginnen
// wie zuvor, sofern genügend Platz vorhanden ist.
builder.ParagraphFormat.PageBreakBefore = pageBreakBefore;

builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

LayoutCollector layoutCollector = new LayoutCollector(doc);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

if (pageBreakBefore)
{
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[0]));
    Assert.AreEqual(2, layoutCollector.GetStartPageIndex(paragraphs[1]));
}
else
{
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[0]));
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[1]));
}

doc.Save(ArtifactsDir + "ParagraphFormat.PageBreakBefore.docx");
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


