---
title: LayoutCollector.LayoutCollector
second_title: Aspose.Words för .NET API Referens
description: LayoutCollector byggare. Initierar en instans av denna klass.
type: docs
weight: 10
url: /sv/net/aspose.words.layout/layoutcollector/layoutcollector/
---
## LayoutCollector constructor

Initierar en instans av denna klass.

```csharp
public LayoutCollector(Document doc)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| doc | Document | Dokumentet som denna samlarinstans kommer att bifogas till. |

### Exempel

Visar hur man kan se sidorna som en nod sträcker sig över.

```csharp
Document doc = new Document();
LayoutCollector layoutCollector = new LayoutCollector(doc);

// Kalla metoden "GetNumPagesSpanned" för att räkna hur många sidor innehållet i vårt dokument sträcker sig.
// Eftersom dokumentet är tomt är antalet sidor för närvarande noll.
Assert.AreEqual(doc, layoutCollector.Document);
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

// Fyll dokumentet med 5 sidor innehåll.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Section 1");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);

// Innan layoutsamlaren måste vi anropa metoden "UpdatePageLayout" för att ge oss
// en korrekt siffra för alla layoutrelaterade mätvärden, till exempel sidantal.
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

layoutCollector.Clear();
doc.UpdatePageLayout();

Assert.AreEqual(5, layoutCollector.GetNumPagesSpanned(doc));

// Vi kan se numren på start- och slutsidorna för alla noder och deras övergripande sidspann.
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);
foreach (Node node in nodes)
{
    Console.WriteLine($"->  NodeType.{node.NodeType}: ");
    Console.WriteLine(
        $"\tStarts on page {layoutCollector.GetStartPageIndex(node)}, ends on page {layoutCollector.GetEndPageIndex(node)}," +
        $" spanning {layoutCollector.GetNumPagesSpanned(node)} pages.");
}

// Vi kan iterera över layoutentiteterna med hjälp av en LayoutEnumerator.
LayoutEnumerator layoutEnumerator = new LayoutEnumerator(doc);

Assert.AreEqual(LayoutEntityType.Page, layoutEnumerator.Type);

// LayoutEnumeratorn kan gå igenom samlingen av layoutentiteter som ett träd.
// Vi kan också tillämpa det på valfri nods motsvarande layoutentitet.
layoutEnumerator.Current = layoutCollector.GetEntity(doc.GetChild(NodeType.Paragraph, 1, true));

Assert.AreEqual(LayoutEntityType.Span, layoutEnumerator.Type);
Assert.AreEqual("¶", layoutEnumerator.Text);
```

### Se även

* class [Document](../../../aspose.words/document/)
* class [LayoutCollector](../)
* namnutrymme [Aspose.Words.Layout](../../layoutcollector/)
* hopsättning [Aspose.Words](../../../)


