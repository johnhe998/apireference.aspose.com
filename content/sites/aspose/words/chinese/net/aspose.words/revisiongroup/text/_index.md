---
title: RevisionGroup.Text
second_title: Aspose.Words for .NET API 参考
description: RevisionGroup 财产. 返回插入/删除/移动的文本或格式更改的描述
type: docs
weight: 30
url: /zh/net/aspose.words/revisiongroup/text/
---
## RevisionGroup.Text property

返回插入/删除/移动的文本或格式更改的描述。

```csharp
public string Text { get; }
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

* class [RevisionGroup](../)
* 命名空间 [Aspose.Words](../../revisiongroup/)
* 部件 [Aspose.Words](../../../)


