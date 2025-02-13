---
title: CompositeNode.RemoveChild
second_title: Aspose.Words for .NET API 参考
description: CompositeNode 方法. 移除指定的子节点
type: docs
weight: 180
url: /zh/net/aspose.words/compositenode/removechild/
---
## CompositeNode.RemoveChild method

移除指定的子节点。

```csharp
public Node RemoveChild(Node oldChild)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| oldChild | Node | 要移除的节点。 |

### 返回值

移除的节点。

### 评论

删除节点后，oldChild 的父级设置为 null。

### 例子

演示如何使用 Node 和 CompositeNode 的方法来删除文档中最后一个部分之前的部分。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// 两个部分是彼此的兄弟。
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// 根据与另一个部分的兄弟关系删除一个部分。
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// 我们删除的部分是第一个，文档只剩下第二个。
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### 也可以看看

* class [Node](../../node/)
* class [CompositeNode](../)
* 命名空间 [Aspose.Words](../../compositenode/)
* 部件 [Aspose.Words](../../../)


