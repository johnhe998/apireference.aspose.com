---
title: RevisionGroupCollection.GetEnumerator
second_title: Aspose.Words für .NET-API-Referenz
description: RevisionGroupCollection methode. Gibt ein Aufzählungsobjekt zurück.
type: docs
weight: 30
url: /de/net/aspose.words/revisiongroupcollection/getenumerator/
---
## RevisionGroupCollection.GetEnumerator method

Gibt ein Aufzählungsobjekt zurück.

```csharp
public IEnumerator<RevisionGroup> GetEnumerator()
```

### Beispiele

Zeigt, wie mit der Sammlung von Revisionen eines Dokuments gearbeitet wird.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
RevisionCollection revisions = doc.Revisions;

// Diese Sammlung selbst hat eine Sammlung von Revisionsgruppen.
// Jede Gruppe ist eine Folge benachbarter Revisionen.
Console.WriteLine($"{revisions.Groups.Count} revision groups:");

// Über die Sammlung von Gruppen iterieren und den Text ausgeben, den die Überarbeitung betrifft.
using (IEnumerator<RevisionGroup> e = revisions.Groups.GetEnumerator())
{
    while (e.MoveNext())
    {
        Console.WriteLine($"\tGroup type \"{e.Current.RevisionType}\", " +
                          $"author: {e.Current.Author}, contents: [{e.Current.Text.Trim()}]");
    }
}

// Jede Ausführung, auf die sich eine Revision auswirkt, erhält ein entsprechendes Revisionsobjekt.
// Die Sammlung der Revisionen ist erheblich größer als die komprimierte Form, die wir oben gedruckt haben,
// abhängig davon, in wie viele Läufe wir das Dokument während der Microsoft Word-Bearbeitung segmentiert haben.
Console.WriteLine($"\n{revisions.Count} revisions:");

using (IEnumerator<Revision> e = revisions.GetEnumerator())
{
    while (e.MoveNext())
    {
        // Ein StyleDefinitionChange wirkt sich ausschließlich auf Stile und nicht auf Dokumentknoten aus. Dies bedeutet den "Elternstil"
        // Die Eigenschaft wird immer verwendet, während der ParentNode immer null ist.
        // Da alle anderen Änderungen Knoten betreffen, wird ParentNode umgekehrt verwendet und ParentStyle ist null.
        if (e.Current.RevisionType == RevisionType.StyleDefinitionChange)
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, style: [{e.Current.ParentStyle.Name}]");
        }
        else
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, contents: [{e.Current.ParentNode.GetText().Trim()}]");
        }
    }
}

// Alle Überarbeitungen über die Sammlung ablehnen und das Dokument in seine ursprüngliche Form zurückversetzen.
revisions.RejectAll();

Assert.AreEqual(0, revisions.Count);
```

### Siehe auch

* class [RevisionGroup](../../revisiongroup/)
* class [RevisionGroupCollection](../)
* namensraum [Aspose.Words](../../revisiongroupcollection/)
* Montage [Aspose.Words](../../../)


