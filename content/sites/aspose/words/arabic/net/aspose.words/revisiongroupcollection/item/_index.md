---
title: RevisionGroupCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: RevisionGroupCollection ملكية. إرجاع مجموعة مراجعة بالفهرس المحدد.
type: docs
weight: 20
url: /ar/net/aspose.words/revisiongroupcollection/item/
---
## RevisionGroupCollection indexer

إرجاع مجموعة مراجعة بالفهرس المحدد.

```csharp
public RevisionGroup this[int index] { get; }
```

### أمثلة

يوضح كيفية الحصول على مجموعة من المراجعات في مستند.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

RevisionGroup revisionGroup = doc.Revisions.Groups[0];
```

### أنظر أيضا

* class [RevisionGroup](../../revisiongroup/)
* class [RevisionGroupCollection](../)
* مساحة الاسم [Aspose.Words](../../revisiongroupcollection/)
* المجسم [Aspose.Words](../../../)


