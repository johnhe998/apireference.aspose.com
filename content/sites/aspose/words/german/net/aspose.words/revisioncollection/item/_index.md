---
title: RevisionCollection.Item
second_title: Aspose.Words für .NET-API-Referenz
description: RevisionCollection eigendom. Gibt eine Revision am angegebenen Index zurück.
type: docs
weight: 30
url: /de/net/aspose.words/revisioncollection/item/
---
## RevisionCollection indexer

Gibt eine Revision am angegebenen Index zurück.

```csharp
public Revision this[int index] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| index | Ein Index in die Sammlung. |

### Bemerkungen

Der Index ist nullbasiert.

Negative Indizes sind zulässig und zeigen den Zugriff von der Rückseite der Sammlung an. Zum Beispiel bedeutet -1 das letzte Element, -2 bedeutet das vorletzte und so weiter.

Wenn der Index größer oder gleich der Anzahl der Elemente in der Liste ist, wird eine Nullreferenz zurückgegeben.

Wenn der Index negativ ist und sein absoluter Wert größer als die Anzahl der Elemente in der Liste ist, wird eine Nullreferenz zurückgegeben.

### Beispiele

Zeigt, wie mit Überarbeitungen in einem Dokument gearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Die normale Bearbeitung des Dokuments zählt nicht als Überarbeitung.
builder.Write("This does not count as a revision. ");

Assert.IsFalse(doc.HasRevisions);

// Um unsere Bearbeitungen als Überarbeitungen zu registrieren, müssen wir einen Autor angeben und dann mit der Nachverfolgung beginnen.
doc.StartTrackRevisions("John Doe", DateTime.Now);

builder.Write("This is revision #1. ");

Assert.IsTrue(doc.HasRevisions);
Assert.AreEqual(1, doc.Revisions.Count);

// Dieses Flag entspricht dem "Review" -> "Tracking" -> Option „Änderungen verfolgen“ in Microsoft Word.
// Die Methode "StartTrackRevisions" hat keinen Einfluss auf ihren Wert,
// und das Dokument verfolgt Revisionen programmgesteuert, obwohl es den Wert "false" hat.
// Wenn wir dieses Dokument mit Microsoft Word öffnen, werden keine Revisionen verfolgt.
Assert.IsFalse(doc.TrackRevisions);

// Wir haben Text mit dem Document Builder hinzugefügt, daher ist die erste Revision eine Revision vom Einfügungstyp.
Revision revision = doc.Revisions[0];
Assert.AreEqual("John Doe", revision.Author);
Assert.AreEqual("This is revision #1. ", revision.ParentNode.GetText());
Assert.AreEqual(RevisionType.Insertion, revision.RevisionType);
Assert.AreEqual(revision.DateTime.Date, DateTime.Now.Date);
Assert.AreEqual(doc.Revisions.Groups[0], revision.Group);

// Eine Ausführung entfernen, um eine Revision vom Typ "Löschen" zu erstellen.
doc.FirstSection.Body.FirstParagraph.Runs[0].Remove();

// Das Hinzufügen einer neuen Revision platziert sie am Anfang der Revisionssammlung.
Assert.AreEqual(RevisionType.Deletion, doc.Revisions[0].RevisionType);
Assert.AreEqual(2, doc.Revisions.Count);

// Überarbeitungen einfügen werden im Dokumentkörper angezeigt, noch bevor wir die Überarbeitung akzeptieren/ablehnen.
// Durch das Ablehnen der Revision werden ihre Knoten aus dem Körper entfernt. Umgekehrt löschen Knoten, aus denen Revisionen bestehen
// Verweilen Sie auch im Dokument, bis wir die Überarbeitung akzeptieren.
Assert.AreEqual("This does not count as a revision. This is revision #1.", doc.GetText().Trim());

// Das Akzeptieren der Löschrevision entfernt den übergeordneten Knoten aus dem Absatztext
// und dann die Revision der Sammlung selbst entfernen.
doc.Revisions[0].Accept();

Assert.AreEqual(1, doc.Revisions.Count);
Assert.AreEqual("This is revision #1.", doc.GetText().Trim());

builder.Writeln("");
builder.Write("This is revision #2.");

// Verschieben Sie nun den Knoten, um einen beweglichen Revisionstyp zu erstellen.
Node node = doc.FirstSection.Body.Paragraphs[1];
Node endNode = doc.FirstSection.Body.Paragraphs[1].NextSibling;
Node referenceNode = doc.FirstSection.Body.Paragraphs[0];

while (node != endNode)
{
    Node nextNode = node.NextSibling;
    doc.FirstSection.Body.InsertBefore(node, referenceNode);
    node = nextNode;
}

Assert.AreEqual(RevisionType.Moving, doc.Revisions[0].RevisionType);
Assert.AreEqual(8, doc.Revisions.Count);
Assert.AreEqual("This is revision #2.\rThis is revision #1. \rThis is revision #2.", doc.GetText().Trim());

// Die verschobene Revision befindet sich jetzt auf Index 1. Lehnen Sie die Revision ab, um ihren Inhalt zu verwerfen.
doc.Revisions[1].Reject();

Assert.AreEqual(6, doc.Revisions.Count);
Assert.AreEqual("This is revision #1. \rThis is revision #2.", doc.GetText().Trim());
```

### Siehe auch

* class [Revision](../../revision/)
* class [RevisionCollection](../)
* namensraum [Aspose.Words](../../revisioncollection/)
* Montage [Aspose.Words](../../../)


