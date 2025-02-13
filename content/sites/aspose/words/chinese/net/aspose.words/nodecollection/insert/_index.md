---
title: NodeCollection.Insert
second_title: Aspose.Words for .NET API 参考
description: NodeCollection 方法. 将一个节点插入到集合中指定索引处
type: docs
weight: 80
url: /zh/net/aspose.words/nodecollection/insert/
---
## NodeCollection.Insert method

将一个节点插入到集合中指定索引处。

```csharp
public void Insert(int index, Node node)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| index | Int32 | 节点的从零开始的索引。 允许负索引，表示从列表后面访问。 例如-1 表示最后一个节点，-2 表示倒数第二个，依此类推。 |
| node | Node | 要插入的节点。 |

### 例外

| 例外 | （健康）状况 |
| --- | --- |
| NotSupportedException | 这 **节点集合**是一个“深”的集合。 |

### 评论

该节点作为子节点插入到从中创建集合的节点对象中。

如果索引等于或大于 Count，则将节点添加到集合的末尾。

如果索引为负且其绝对值大于 Count，则将节点添加到集合的末尾。

如果 newChild 已经在树中，则首先将其移除。

如果要插入的节点是从另一个文档创建的，则应使用 [`ImportNode`](../../documentbase/importnode/)将节点导入当前文档。 然后可以将导入的节点插入到当前文档中。

### 例子

展示如何使用 NodeCollection。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 通过使用 DocumentBuilder 插入运行，将文本添加到文档中。
builder.Write("Run 1. ");
builder.Write("Run 2. ");

// 每次调用“Write”方法都会创建一个新的 Run，
// 然后出现在父段落的 RunCollection 中。
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;

Assert.AreEqual(2, runs.Count);

// 我们也可以手动将节点插入到 RunCollection 中。
Run newRun = new Run(doc, "Run 3. ");
runs.Insert(3, newRun);

Assert.True(runs.Contains(newRun));
Assert.AreEqual("Run 1. Run 2. Run 3.", doc.GetText().Trim());

// 访问单个运行并删除它们以从文档中删除它们的文本。
Run run = runs[1];
runs.Remove(run);

Assert.AreEqual("Run 1. Run 3.", doc.GetText().Trim());
Assert.NotNull(run);
Assert.False(runs.Contains(run));
```

### 也可以看看

* class [Node](../../node/)
* class [NodeCollection](../)
* 命名空间 [Aspose.Words](../../nodecollection/)
* 部件 [Aspose.Words](../../../)


