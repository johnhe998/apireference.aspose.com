---
title: Paragraph.IsInsertRevision
second_title: Aspose.Words für .NET-API-Referenz
description: Paragraph eigendom. Gibt true zurück wenn dieses Objekt in Microsoft Word eingefügt wurde während die Änderungsverfolgung aktiviert war.
type: docs
weight: 110
url: /de/net/aspose.words/paragraph/isinsertrevision/
---
## Paragraph.IsInsertRevision property

Gibt „true“ zurück, wenn dieses Objekt in Microsoft Word eingefügt wurde, während die Änderungsverfolgung aktiviert war.

```csharp
public bool IsInsertRevision { get; }
```

### Beispiele

Zeigt, wie mit Überarbeitungsabsätzen gearbeitet wird.

```csharp
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Die obigen Absätze sind keine Überarbeitungen.
// Absätze, die wir nach dem Start der Revisionsverfolgung hinzufügen, werden als „Einfügen“-Revisionen registriert.
doc.StartTrackRevisions("John Doe", DateTime.Now);

para = body.AppendParagraph("Paragraph 4. ");

Assert.True(para.IsInsertRevision);

// Absätze, die wir nach dem Start der Revisionsverfolgung entfernen, werden als "gelöschte" Revisionen registriert.
ParagraphCollection paragraphs = body.Paragraphs;

Assert.AreEqual(4, paragraphs.Count);

para = paragraphs[2];
para.Remove();

// Solche Absätze bleiben bestehen, bis wir die Löschüberarbeitung entweder akzeptieren oder ablehnen.
// Durch das Akzeptieren der Überarbeitung wird der Absatz endgültig entfernt,
// und die Überarbeitung abzulehnen, wird sie im Dokument belassen, als ob wir sie nie gelöscht hätten.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Akzeptiere die Überarbeitung und vergewissere dich dann, dass der Absatz weg ist.
doc.AcceptAllRevisions();

Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
Assert.AreEqual(
    "Paragraph 1. \r" +
    "Paragraph 2. \r" +
    "Paragraph 4.", doc.GetText().Trim());
```

### Siehe auch

* class [Paragraph](../)
* namensraum [Aspose.Words](../../paragraph/)
* Montage [Aspose.Words](../../../)


