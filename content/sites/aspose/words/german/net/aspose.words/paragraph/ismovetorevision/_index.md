---
title: Paragraph.IsMoveToRevision
second_title: Aspose.Words für .NET-API-Referenz
description: Paragraph eigendom. gibt zurück Stimmt wenn dieses Objekt in Microsoft Word verschoben eingefügt wurde während die Änderungsnachverfolgung aktiviert war.
type: docs
weight: 140
url: /de/net/aspose.words/paragraph/ismovetorevision/
---
## Paragraph.IsMoveToRevision property

gibt zurück **Stimmt** wenn dieses Objekt in Microsoft Word verschoben (eingefügt) wurde, während die Änderungsnachverfolgung aktiviert war.

```csharp
public bool IsMoveToRevision { get; }
```

### Beispiele

Zeigt, wie überprüft wird, ob es sich bei einem Absatz um eine verschobene Überarbeitung handelt.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Dieses Dokument enthält "Move"-Revisionen, die erscheinen, wenn wir Text mit dem Cursor markieren,
// und ziehen Sie es dann, um es an eine andere Position zu verschieben
// beim Verfolgen von Revisionen in Microsoft Word über "Review" -> "Änderungen verfolgen".
Assert.AreEqual(6, doc.Revisions.Count(r => r.RevisionType == RevisionType.Moving));

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

// Verschiebungsrevisionen bestehen aus Paaren von "Move from"- und "Move to"-Revisionen. 
// Diese Überarbeitungen sind potenzielle Änderungen am Dokument, die wir entweder akzeptieren oder ablehnen können.
// Bevor wir eine Move-Revision akzeptieren/ablehnen, wird das Dokument
// muss sowohl die Abfahrts- als auch die Ankunftsziele des Textes verfolgen.
// Der zweite und der vierte Absatz definieren eine solche Überarbeitung und haben daher beide den gleichen Inhalt.
Assert.AreEqual(paragraphs[1].GetText(), paragraphs[3].GetText());

// Die „Move from“-Revision ist der Absatz, aus dem wir den Text gezogen haben.
// Wenn wir die Überarbeitung akzeptieren, verschwindet dieser Absatz,
// und der andere bleibt bestehen und ist keine Revision mehr.
Assert.True(paragraphs[1].IsMoveFromRevision);

// Die Revision „Verschieben nach“ ist der Absatz, in den wir den Text gezogen haben.
// Wenn wir die Überarbeitung ablehnen, verschwindet stattdessen dieser Absatz und der andere bleibt bestehen.
Assert.True(paragraphs[3].IsMoveToRevision);
```

### Siehe auch

* class [Paragraph](../)
* namensraum [Aspose.Words](../../paragraph/)
* Montage [Aspose.Words](../../../)


