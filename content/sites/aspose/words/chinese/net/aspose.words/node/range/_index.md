---
title: Node.Range
second_title: Aspose.Words for .NET API 参考
description: Node 财产. 返回一个 范围表示此节点中包含的文档部分的对象
type: docs
weight: 80
url: /zh/net/aspose.words/node/range/
---
## Node.Range property

返回一个 **范围**表示此节点中包含的文档部分的对象。

```csharp
public Range Range { get; }
```

### 例子

显示如何从范围中删除所有节点。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 将文本添加到文档的第一个部分，然后添加另一个部分。
builder.Write("Section 1. ");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Write("Section 2.");

Assert.AreEqual("Section 1. \fSection 2.", doc.GetText().Trim());

// 通过删除所有节点来完全删除第一部分
// 在其范围内，包括部分本身。
doc.Sections[0].Range.Delete();

Assert.AreEqual(1, doc.Sections.Count);
Assert.AreEqual("Section 2.", doc.GetText().Trim());
```

### 也可以看看

* class [Range](../../range/)
* class [Node](../)
* 命名空间 [Aspose.Words](../../node/)
* 部件 [Aspose.Words](../../../)


