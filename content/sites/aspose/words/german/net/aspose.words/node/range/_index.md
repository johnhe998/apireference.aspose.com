---
title: Node.Range
second_title: Aspose.Words für .NET-API-Referenz
description: Node eigendom. Gibt a zurück Bereich Objekt das den Teil eines Dokuments darstellt das in diesem Knoten enthalten ist.
type: docs
weight: 80
url: /de/net/aspose.words/node/range/
---
## Node.Range property

Gibt a zurück **Bereich** Objekt, das den Teil eines Dokuments darstellt, das in diesem Knoten enthalten ist.

```csharp
public Range Range { get; }
```

### Beispiele

Zeigt, wie alle Knoten aus einem Bereich gelöscht werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Text zum ersten Abschnitt im Dokument hinzufügen und dann einen weiteren Abschnitt hinzufügen.
builder.Write("Section 1. ");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Write("Section 2.");

Assert.AreEqual("Section 1. \fSection 2.", doc.GetText().Trim());

// Entfernen Sie den ersten Abschnitt vollständig, indem Sie alle Knoten entfernen
// innerhalb seines Bereichs, einschließlich des Abschnitts selbst.
doc.Sections[0].Range.Delete();

Assert.AreEqual(1, doc.Sections.Count);
Assert.AreEqual("Section 2.", doc.GetText().Trim());
```

### Siehe auch

* class [Range](../../range/)
* class [Node](../)
* namensraum [Aspose.Words](../../node/)
* Montage [Aspose.Words](../../../)


