---
title: Node.PreviousSibling
second_title: Aspose.Words für .NET-API-Referenz
description: Node eigendom. Ruft den Knoten unmittelbar vor diesem Knoten ab.
type: docs
weight: 70
url: /de/net/aspose.words/node/previoussibling/
---
## Node.PreviousSibling property

Ruft den Knoten unmittelbar vor diesem Knoten ab.

```csharp
public Node PreviousSibling { get; }
```

### Bemerkungen

Wenn es keinen vorhergehenden Knoten gibt, wird eine Null zurückgegeben.

### Beispiele

Zeigt, wie die Methoden von Node und CompositeNode verwendet werden, um einen Abschnitt vor dem letzten Abschnitt im Dokument zu entfernen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// Beide Abschnitte sind Geschwister voneinander.
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// Einen Abschnitt basierend auf seiner Geschwisterbeziehung mit einem anderen Abschnitt entfernen.
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// Der Abschnitt, den wir entfernt haben, war der erste, sodass das Dokument nur den zweiten enthält.
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### Siehe auch

* class [Node](../)
* namensraum [Aspose.Words](../../node/)
* Montage [Aspose.Words](../../../)


