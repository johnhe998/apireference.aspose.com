---
title: RevisionGroup.RevisionType
second_title: Справочник по API Aspose.Words для .NET
description: RevisionGroup свойство. Получает тип ревизий включенных в эту группу.
type: docs
weight: 20
url: /ru/net/aspose.words/revisiongroup/revisiontype/
---
## RevisionGroup.RevisionType property

Получает тип ревизий, включенных в эту группу.

```csharp
public RevisionType RevisionType { get; }
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

* enum [RevisionType](../../revisiontype/)
* class [RevisionGroup](../)
* пространство имен [Aspose.Words](../../revisiongroup/)
* сборка [Aspose.Words](../../../)


