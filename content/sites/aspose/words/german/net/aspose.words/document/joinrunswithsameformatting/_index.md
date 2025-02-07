---
title: Document.JoinRunsWithSameFormatting
second_title: Aspose.Words für .NET-API-Referenz
description: Document methode. Verbindet Läufe mit derselben Formatierung in allen Absätzen des Dokuments.
type: docs
weight: 600
url: /de/net/aspose.words/document/joinrunswithsameformatting/
---
## Document.JoinRunsWithSameFormatting method

Verbindet Läufe mit derselben Formatierung in allen Absätzen des Dokuments.

```csharp
public int JoinRunsWithSameFormatting()
```

### Rückgabewert

Anzahl der durchgeführten Joins. Wann **N** Aneinandergrenzende Läufe werden zusammengefügt, sie zählen als **N - 1** schließt sich an.

### Bemerkungen

Dies ist eine Optimierungsmethode. Einige Dokumente enthalten benachbarte Läufe mit gleicher Formatierung. Dies tritt normalerweise auf, wenn ein Dokument intensiv manuell bearbeitet wurde. Sie können die Dokumentgröße reduzieren und die weitere Verarbeitung beschleunigen, indem Sie diese Läufe zusammenfügen.

Der Betrieb prüft alle[`Paragraph`](../../paragraph/) Knoten im Dokument für angrenzend[`Run`](../../run/) Knoten mit identischen Eigenschaften. Es ignoriert eindeutige Bezeichner, die zum Verfolgen von Bearbeitungssitzungen der Erstellung und Änderung von run verwendet werden. Beim ersten Durchlauf in jeder Verbindungssequenz wird der gesamte Text akkumuliert. Verbleibende Läufe werden aus dem Dokument gelöscht.

### Beispiele

Zeigt, wie Sie Läufe in einem Dokument verbinden, um unnötige Läufe zu reduzieren.

```csharp
// Öffnen Sie ein Dokument, das benachbarte Textpassagen mit identischer Formatierung enthält,
// was häufig auftritt, wenn wir denselben Absatz mehrmals in Microsoft Word bearbeiten.
Document doc = new Document(MyDir + "Rendering.docx");

// Wenn eine beliebige Anzahl dieser Läufe mit identischer Formatierung benachbart sind,
// dann kann das Dokument vereinfacht werden.
Assert.AreEqual(317, doc.GetChildNodes(NodeType.Run, true).Count);

// Kombinieren Sie solche Läufe mit dieser Methode und überprüfen Sie die Anzahl der stattfindenden Laufverknüpfungen.
Assert.AreEqual(121, doc.JoinRunsWithSameFormatting());

// Die Anzahl der Joins und die Anzahl der Runs, die wir nach dem Join haben
// sollte die Anzahl der Läufe addieren, die wir ursprünglich hatten.
Assert.AreEqual(196, doc.GetChildNodes(NodeType.Run, true).Count);
```

### Siehe auch

* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


