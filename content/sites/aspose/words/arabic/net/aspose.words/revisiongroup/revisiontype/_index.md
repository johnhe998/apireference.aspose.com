---
title: RevisionGroup.RevisionType
second_title: Aspose.Words لمراجع .NET API
description: RevisionGroup ملكية. الحصول على نوع المراجعات المضمنة في هذه المجموعة.
type: docs
weight: 20
url: /ar/net/aspose.words/revisiongroup/revisiontype/
---
## RevisionGroup.RevisionType property

الحصول على نوع المراجعات المضمنة في هذه المجموعة.

```csharp
public RevisionType RevisionType { get; }
```

### أمثلة

يوضح كيفية طباعة معلومات حول مجموعة من المراجعات في مستند.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

Assert.AreEqual(7, doc.Revisions.Groups.Count);

foreach (RevisionGroup group in doc.Revisions.Groups)
{
    Console.WriteLine(
        $"Revision author: {group.Author}; Revision type: {group.RevisionType} \n\tRevision text: {group.Text}");
}
```

### أنظر أيضا

* enum [RevisionType](../../revisiontype/)
* class [RevisionGroup](../)
* مساحة الاسم [Aspose.Words](../../revisiongroup/)
* المجسم [Aspose.Words](../../../)


