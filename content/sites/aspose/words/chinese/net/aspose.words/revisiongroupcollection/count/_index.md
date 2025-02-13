---
title: RevisionGroupCollection.Count
second_title: Aspose.Words for .NET API 参考
description: RevisionGroupCollection 财产. 返回集合中的修订组数
type: docs
weight: 10
url: /zh/net/aspose.words/revisiongroupcollection/count/
---
## RevisionGroupCollection.Count property

返回集合中的修订组数。

```csharp
public int Count { get; }
```

### 例子

显示如何在文档中打印有关一组修订的信息。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

Assert.AreEqual(7, doc.Revisions.Groups.Count);

foreach (RevisionGroup group in doc.Revisions.Groups)
{
    Console.WriteLine(
        $"Revision author: {group.Author}; Revision type: {group.RevisionType} \n\tRevision text: {group.Text}");
}
```

### 也可以看看

* class [RevisionGroupCollection](../)
* 命名空间 [Aspose.Words](../../revisiongroupcollection/)
* 部件 [Aspose.Words](../../../)


