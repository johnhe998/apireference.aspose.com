---
title: RevisionGroupCollection.Item
second_title: Aspose.Words for .NET API 参考
description: RevisionGroupCollection 财产. 返回指定索引处的修订组
type: docs
weight: 20
url: /zh/net/aspose.words/revisiongroupcollection/item/
---
## RevisionGroupCollection indexer

返回指定索引处的修订组。

```csharp
public RevisionGroup this[int index] { get; }
```

### 例子

显示如何在文档中获取一组修订。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

RevisionGroup revisionGroup = doc.Revisions.Groups[0];
```

### 也可以看看

* class [RevisionGroup](../../revisiongroup/)
* class [RevisionGroupCollection](../)
* 命名空间 [Aspose.Words](../../revisiongroupcollection/)
* 部件 [Aspose.Words](../../../)


