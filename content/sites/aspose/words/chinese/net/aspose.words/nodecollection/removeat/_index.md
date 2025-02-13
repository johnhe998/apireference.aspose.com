---
title: NodeCollection.RemoveAt
second_title: Aspose.Words for .NET API 参考
description: NodeCollection 方法. 从集合和文档中删除指定索引处的节点
type: docs
weight: 100
url: /zh/net/aspose.words/nodecollection/removeat/
---
## NodeCollection.RemoveAt method

从集合和文档中删除指定索引处的节点。

```csharp
public void RemoveAt(int index)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| index | Int32 | 节点的从零开始的索引。 允许负索引，表示从列表后面访问。 例如-1 表示最后一个节点，-2 表示倒数第二个，依此类推。 |

### 例子

显示如何在文档中添加和删除部分。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

Assert.AreEqual("Section 1\x000cSection 2", doc.GetText().Trim());

// 从文档中删除第一部分。
doc.Sections.RemoveAt(0);

Assert.AreEqual("Section 2", doc.GetText().Trim());

// 将现在第一部分的副本附加到文档的末尾。
int lastSectionIdx = doc.Sections.Count - 1;
Section newSection = doc.Sections[lastSectionIdx].Clone();
doc.Sections.Add(newSection);

Assert.AreEqual("Section 2\x000cSection 2", doc.GetText().Trim());
```

### 也可以看看

* class [NodeCollection](../)
* 命名空间 [Aspose.Words](../../nodecollection/)
* 部件 [Aspose.Words](../../../)


