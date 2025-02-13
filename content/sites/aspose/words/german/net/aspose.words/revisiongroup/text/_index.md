---
title: RevisionGroup.Text
second_title: Aspose.Words für .NET-API-Referenz
description: RevisionGroup eigendom. Gibt eingefügten/gelöschten/verschobenen Text oder eine Beschreibung der Formatänderung zurück.
type: docs
weight: 30
url: /de/net/aspose.words/revisiongroup/text/
---
## RevisionGroup.Text property

Gibt eingefügten/gelöschten/verschobenen Text oder eine Beschreibung der Formatänderung zurück.

```csharp
public string Text { get; }
```

### Beispiele

Zeigt, wie Informationen zu einer Gruppe von Revisionen in einem Dokument gedruckt werden.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

Assert.AreEqual(7, doc.Revisions.Groups.Count);

foreach (RevisionGroup group in doc.Revisions.Groups)
{
    Console.WriteLine(
        $"Revision author: {group.Author}; Revision type: {group.RevisionType} \n\tRevision text: {group.Text}");
}
```

### Siehe auch

* class [RevisionGroup](../)
* namensraum [Aspose.Words](../../revisiongroup/)
* Montage [Aspose.Words](../../../)


