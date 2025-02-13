---
title: CompositeNode.RemoveChild
second_title: Aspose.Words för .NET API Referens
description: CompositeNode metod. Tar bort den angivna underordnade noden.
type: docs
weight: 180
url: /sv/net/aspose.words/compositenode/removechild/
---
## CompositeNode.RemoveChild method

Tar bort den angivna underordnade noden.

```csharp
public Node RemoveChild(Node oldChild)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| oldChild | Node | Noden att ta bort. |

### Returvärde

Den borttagna noden.

### Anmärkningar

Föräldern till oldChild är inställd på null efter att noden har tagits bort.

### Exempel

Visar hur man använder metoderna för Node och CompositeNode för att ta bort ett avsnitt före det sista avsnittet i dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// Båda sektionerna är syskon till varandra.
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// Ta bort ett avsnitt baserat på dess syskonförhållande med ett annat avsnitt.
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// Avsnittet vi tog bort var det första, vilket lämnade dokumentet med bara det andra.
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### Se även

* class [Node](../../node/)
* class [CompositeNode](../)
* namnutrymme [Aspose.Words](../../compositenode/)
* hopsättning [Aspose.Words](../../../)


