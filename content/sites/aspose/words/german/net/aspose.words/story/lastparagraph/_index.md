---
title: Story.LastParagraph
second_title: Aspose.Words für .NET-API-Referenz
description: Story eigendom. Ruft den letzten Absatz in der Story ab.
type: docs
weight: 20
url: /de/net/aspose.words/story/lastparagraph/
---
## Story.LastParagraph property

Ruft den letzten Absatz in der Story ab.

```csharp
public Paragraph LastParagraph { get; }
```

### Beispiele

Zeigt, wie die Cursorposition eines DocumentBuilder zu einem angegebenen Knoten verschoben wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Run 1. ");

// Der Document Builder hat einen Cursor, der als Teil des Dokuments fungiert
// wo der Builder neue Knoten anfügt, wenn wir seine Dokumentkonstruktionsmethoden verwenden.
// Dieser Cursor funktioniert genauso wie der blinkende Cursor von Microsoft Word,
// und es endet auch immer unmittelbar nach jedem Knoten, den der Builder gerade eingefügt hat.
// Um Inhalt an einen anderen Teil des Dokuments anzuhängen,
// Mit der Methode "MoveTo" können wir den Cursor zu einem anderen Knoten bewegen.
// Der Cursor steht jetzt vor dem Knoten, zu dem wir ihn verschoben haben.
// Wenn Sie einen zweiten Lauf hinzufügen, wird dieser vor dem ersten Lauf eingefügt.
builder.Writeln("Run 2. ");

Assert.AreEqual("Run 2. \rRun 1.", doc.GetText().Trim());

// Bewegen Sie den Cursor an das Ende des Dokuments, um wie zuvor mit dem Anhängen von Text an das Ende fortzufahren.
builder.MoveTo(doc.LastSection.Body.LastParagraph);
builder.Writeln("Run 3. ");

Assert.AreEqual("Run 2. \rRun 1. \rRun 3.", doc.GetText().Trim());
```

### Siehe auch

* class [Paragraph](../../paragraph/)
* class [Story](../)
* namensraum [Aspose.Words](../../story/)
* Montage [Aspose.Words](../../../)


