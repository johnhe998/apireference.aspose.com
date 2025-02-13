---
title: Class SectionCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.SectionCollection 班级. 集合 部分文档中的对象
type: docs
weight: 5450
url: /zh/net/aspose.words/sectioncollection/
---
## SectionCollection class

集合 **部分**文档中的对象。

```csharp
public class SectionCollection : NodeCollection
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | 获取集合中的节点数。 |
| [Item](../../aspose.words/sectioncollection/item/) { get; } | 检索给定索引处的节。 (2 indexers) |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | 将一个节点添加到集合的末尾。 |
| [Clear](../../aspose.words/nodecollection/clear/)() | 从此集合和文档中删除所有节点。 |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | 确定一个节点是否在集合中。 |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | 在节点集合上提供简单的“foreach”样式迭代。 |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | 返回指定节点的从零开始的索引。 |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | 将一个节点插入到集合中指定索引处。 |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | 从集合和文档中删除节点。 |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | 从集合和文档中删除指定索引处的节点。 |
| [ToArray](../../aspose.words/sectioncollection/toarray/#toarray_1)() | 将集合中的所有部分复制到新的部分数组中。 (2 methods) |

### 评论

Microsoft Word 文档可以包含多个部分。要在 Microsoft Word 中创建节， 选择插入/中断命令并选择中断类型。中断指定节是在新页面上还是在同一页面上开始 。

以编程方式插入和删除部分可用于在邮件合并期间自定义文档produced 。如果文档需要根据某些条件具有不同的内容或部分内容，那么您可以创建一个包含 多个部分的“主”文档，并在邮件合并之前或之后删除一些部分。

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

* class [NodeCollection](../nodecollection/)
* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


