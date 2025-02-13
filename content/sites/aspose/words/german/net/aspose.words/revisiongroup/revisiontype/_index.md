---
title: RevisionGroup.RevisionType
second_title: Aspose.Words für .NET-API-Referenz
description: RevisionGroup eigendom. Ruft den Revisionstyp ab der in dieser Gruppe enthalten ist.
type: docs
weight: 20
url: /de/net/aspose.words/revisiongroup/revisiontype/
---
## RevisionGroup.RevisionType property

Ruft den Revisionstyp ab, der in dieser Gruppe enthalten ist.

```csharp
public RevisionType RevisionType { get; }
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

* enum [RevisionType](../../revisiontype/)
* class [RevisionGroup](../)
* namensraum [Aspose.Words](../../revisiongroup/)
* Montage [Aspose.Words](../../../)


