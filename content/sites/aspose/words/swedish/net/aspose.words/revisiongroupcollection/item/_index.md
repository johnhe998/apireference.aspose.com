---
title: RevisionGroupCollection.Item
second_title: Aspose.Words för .NET API Referens
description: RevisionGroupCollection fast egendom. Returnerar en revisionsgrupp vid det angivna indexet.
type: docs
weight: 20
url: /sv/net/aspose.words/revisiongroupcollection/item/
---
## RevisionGroupCollection indexer

Returnerar en revisionsgrupp vid det angivna indexet.

```csharp
public RevisionGroup this[int index] { get; }
```

### Exempel

Visar hur man får en grupp av revisioner i ett dokument.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

RevisionGroup revisionGroup = doc.Revisions.Groups[0];
```

### Se även

* class [RevisionGroup](../../revisiongroup/)
* class [RevisionGroupCollection](../)
* namnutrymme [Aspose.Words](../../revisiongroupcollection/)
* hopsättning [Aspose.Words](../../../)


