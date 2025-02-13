---
title: Class RevisionGroupCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.RevisionGroupCollection فصل. مجموعة منRevisionGroup الكائنات التي تمثل مجموعات المراجعة في المستند.
type: docs
weight: 4530
url: /ar/net/aspose.words/revisiongroupcollection/
---
## RevisionGroupCollection class

مجموعة من[`RevisionGroup`](../revisiongroup/) الكائنات التي تمثل مجموعات المراجعة في المستند.

```csharp
public sealed class RevisionGroupCollection : IEnumerable<RevisionGroup>
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words/revisiongroupcollection/count/) { get; } | إرجاع عدد مجموعات المراجعة في المجموعة. |
| [Item](../../aspose.words/revisiongroupcollection/item/) { get; } | إرجاع مجموعة مراجعة بالفهرس المحدد. |

## طُرق

| اسم | وصف |
| --- | --- |
| [GetEnumerator](../../aspose.words/revisiongroupcollection/getenumerator/)() | إرجاع كائن العداد . |

### ملاحظات

لا تقوم بإنشاء نسخ من هذه الفئة مباشرة. استخدم ال[`Groups`](../revisioncollection/groups/) للحصول على مجموعات المراجعة موجودة في المستند.

### أمثلة

يوضح كيفية الحصول على مجموعة من المراجعات في مستند.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

RevisionGroup revisionGroup = doc.Revisions.Groups[0];
```

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

* class [RevisionGroup](../revisiongroup/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


