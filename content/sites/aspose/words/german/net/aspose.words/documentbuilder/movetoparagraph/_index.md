---
title: DocumentBuilder.MoveToParagraph
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Bewegt den Cursor zu einem Absatz im aktuellen Abschnitt.
type: docs
weight: 540
url: /de/net/aspose.words/documentbuilder/movetoparagraph/
---
## DocumentBuilder.MoveToParagraph method

Bewegt den Cursor zu einem Absatz im aktuellen Abschnitt.

```csharp
public void MoveToParagraph(int paragraphIndex, int characterIndex)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| paragraphIndex | Int32 | Der Index des Absatzes, zu dem verschoben werden soll. |
| characterIndex | Int32 | Der Index des Zeichens innerhalb des Absatzes. Mit einem negativen Wert können Sie eine Position vom Ende des Absatzes angeben. Verwenden Sie -1, um zum Ende von des Absatzes zu gehen. |

### Bemerkungen

Die Navigation wird innerhalb des aktuellen Artikels des aktuellen Abschnitts durchgeführt. Das heißt, wenn Sie den Cursor auf die primäre Überschrift des ersten Abschnitts bewegt haben, , dann gibt der Absatzindex den Index des Absatzes innerhalb dieser Überschrift dieses Abschnitts an.

Wenn der Absatzindex größer oder gleich 0 ist, gibt er einen Index von am Anfang des Abschnitts an, wobei 0 der erste Absatz ist. Wenn der Absatzindex kleiner als 0, ist, wurde ein Index vom Ende des Abschnitts angegeben, wobei -1 der letzte Absatz ist.

### Beispiele

Zeigt, wie die Cursorposition eines Builders zu einem angegebenen Absatz verschoben wird.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(22, paragraphs.Count);

// Document Builder erstellen, um das Dokument zu bearbeiten. Der Cursor des Erbauers,
// Das ist der Punkt, an dem neue Knoten eingefügt werden, wenn wir seine Dokumentkonstruktionsmethoden aufrufen,
// befindet sich derzeit am Anfang des Dokuments.
DocumentBuilder builder = new DocumentBuilder(doc);

Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// Bewegen Sie diesen Cursor zu einem anderen Absatz, um diesen Cursor vor diesen Absatz zu platzieren.
builder.MoveToParagraph(2, 0);
// Jeder neue Inhalt, den wir hinzufügen, wird an dieser Stelle eingefügt.
builder.Writeln("This is a new third paragraph. ");
```

### Siehe auch

* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


