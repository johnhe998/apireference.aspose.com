---
title: Class RevisionGroupCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.RevisionGroupCollection 班级. 集合RevisionGroup代表文档中修订组的对象
type: docs
weight: 4530
url: /zh/net/aspose.words/revisiongroupcollection/
---
## RevisionGroupCollection class

集合[`RevisionGroup`](../revisiongroup/)代表文档中修订组的对象。

```csharp
public sealed class RevisionGroupCollection : IEnumerable<RevisionGroup>
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words/revisiongroupcollection/count/) { get; } | 返回集合中的修订组数。 |
| [Item](../../aspose.words/revisiongroupcollection/item/) { get; } | 返回指定索引处的修订组。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [GetEnumerator](../../aspose.words/revisiongroupcollection/getenumerator/)() | 返回一个枚举器对象。 |

### 评论

您不直接创建此类的实例。使用[`Groups`](../revisioncollection/groups/) 属性以获取文档中存在的修订组。

### 例子

显示如何在文档中获取一组修订。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

RevisionGroup revisionGroup = doc.Revisions.Groups[0];
```

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

* class [RevisionGroup](../revisiongroup/)
* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


