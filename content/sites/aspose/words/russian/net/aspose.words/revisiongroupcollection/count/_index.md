---
title: RevisionGroupCollection.Count
second_title: Справочник по API Aspose.Words для .NET
description: RevisionGroupCollection свойство. Возвращает количество групп ревизий в коллекции.
type: docs
weight: 10
url: /ru/net/aspose.words/revisiongroupcollection/count/
---
## RevisionGroupCollection.Count property

Возвращает количество групп ревизий в коллекции.

```csharp
public int Count { get; }
```

### Примеры

Показывает, как распечатать информацию о группе редакций в документе.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

Assert.AreEqual(7, doc.Revisions.Groups.Count);

foreach (RevisionGroup group in doc.Revisions.Groups)
{
    Console.WriteLine(
        $"Revision author: {group.Author}; Revision type: {group.RevisionType} \n\tRevision text: {group.Text}");
}
```

### Смотрите также

* class [RevisionGroupCollection](../)
* пространство имен [Aspose.Words](../../revisiongroupcollection/)
* сборка [Aspose.Words](../../../)


