---
title: RevisionGroup.Author
second_title: Aspose.Words for .NET API Referansı
description: RevisionGroup mülk. Bu revizyon grubunun yazarını alır.
type: docs
weight: 10
url: /tr/net/aspose.words/revisiongroup/author/
---
## RevisionGroup.Author property

Bu revizyon grubunun yazarını alır.

```csharp
public string Author { get; }
```

### Örnekler

Bir belgedeki bir grup düzeltme hakkındaki bilgilerin nasıl yazdırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

Assert.AreEqual(7, doc.Revisions.Groups.Count);

foreach (RevisionGroup group in doc.Revisions.Groups)
{
    Console.WriteLine(
        $"Revision author: {group.Author}; Revision type: {group.RevisionType} \n\tRevision text: {group.Text}");
}
```

### Ayrıca bakınız

* class [RevisionGroup](../)
* ad alanı [Aspose.Words](../../revisiongroup/)
* toplantı [Aspose.Words](../../../)


