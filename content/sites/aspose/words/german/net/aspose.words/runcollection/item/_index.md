---
title: RunCollection.Item
second_title: Aspose.Words für .NET-API-Referenz
description: RunCollection eigendom. Ruft a Laufen am angegebenen Index.
type: docs
weight: 10
url: /de/net/aspose.words/runcollection/item/
---
## RunCollection indexer

Ruft a **Laufen** am angegebenen Index.

```csharp
public Run this[int index] { get; }
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

Zeigt, wie der Revisionstyp eines Inline-Knotens bestimmt wird.

```csharp
Document doc = new Document(MyDir + "Revision runs.docx");

// Wenn wir das Dokument bearbeiten, während die Option „Änderungen nachverfolgen“ unter „Überprüfen“ -> Verfolgung,
// in Microsoft Word aktiviert ist, zählen die von uns vorgenommenen Änderungen als Überarbeitungen.
// Wenn wir ein Dokument mit Aspose.Words bearbeiten, können wir mit der Nachverfolgung von Revisionen beginnen
// die Methode „StartTrackRevisions“ des Dokuments aufrufen und die Nachverfolgung mit der Methode „StopTrackRevisions“ beenden.
// Wir können entweder Überarbeitungen akzeptieren, um sie in das Dokument zu integrieren
// oder sie ablehnen, um die vorgeschlagene Änderung wirksam zu ändern.
Assert.AreEqual(6, doc.Revisions.Count);

// Der übergeordnete Knoten einer Revision ist der Lauf, den die Revision betrifft. Ein Lauf ist ein Inline-Knoten.
Run run = (Run)doc.Revisions[0].ParentNode;

Paragraph firstParagraph = run.ParentParagraph;
RunCollection runs = firstParagraph.Runs;

Assert.AreEqual(6, runs.ToArray().Length);

// Nachfolgend sind fünf Arten von Revisionen aufgeführt, die einen Inline-Knoten kennzeichnen können.
// 1 - Eine "insert"-Revision:
// Diese Überarbeitung tritt auf, wenn wir Text einfügen, während wir Änderungen verfolgen.
Assert.IsTrue(runs[2].IsInsertRevision);

// 2 - Eine "Format"-Revision:
// Diese Überarbeitung tritt auf, wenn wir die Formatierung von Text ändern, während wir Änderungen nachverfolgen.
Assert.IsTrue(runs[2].IsFormatRevision);

// 3 - Eine "Move from"-Revision:
// Wenn wir Text in Microsoft Word markieren und ihn dann an eine andere Stelle im Dokument ziehen
// Beim Nachverfolgen von Änderungen werden zwei Revisionen angezeigt.
// Die „move from“-Revision ist eine Kopie des ursprünglichen Textes, bevor wir ihn verschoben haben.
Assert.IsTrue(runs[4].IsMoveFromRevision);

// 4 - Eine "Verschieben"-Revision:
// Die "move to"-Revision ist der Text, den wir an seine neue Position im Dokument verschoben haben.
// „Move from“- und „move to“-Revisionen erscheinen paarweise für jede Move-Revision, die wir durchführen.
// Das Akzeptieren einer Move-Revision löscht die "Move from"-Revision und ihren Text,
// und behält den Text aus der "move to"-Revision.
// Das Ablehnen einer Move-Revision behält umgekehrt die "Move from"-Revision und löscht die "Move to"-Revision.
Assert.IsTrue(runs[1].IsMoveToRevision);

// 5 - Eine "Lösch"-Revision:
// Diese Überarbeitung tritt auf, wenn wir Text löschen, während wir Änderungen nachverfolgen. Wenn wir solchen Text löschen,
// es bleibt als Überarbeitung im Dokument, bis wir entweder die Überarbeitung akzeptieren,
// wodurch der Text endgültig gelöscht wird, oder die Überarbeitung abgelehnt wird, wodurch der von uns gelöschte Text dort bleibt, wo er war.
Assert.IsTrue(runs[5].IsDeleteRevision);
```

### Siehe auch

* class [Run](../../run/)
* class [RunCollection](../)
* namensraum [Aspose.Words](../../runcollection/)
* Montage [Aspose.Words](../../../)


