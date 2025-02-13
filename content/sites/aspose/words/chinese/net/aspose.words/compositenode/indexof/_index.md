---
title: CompositeNode.IndexOf
second_title: Aspose.Words for .NET API 参考
description: CompositeNode 方法. 返回子节点数组中指定子节点的索引
type: docs
weight: 130
url: /zh/net/aspose.words/compositenode/indexof/
---
## CompositeNode.IndexOf method

返回子节点数组中指定子节点的索引。

```csharp
public int IndexOf(Node child)
```

### 评论

如果在子节点中找不到该节点，则返回 -1。

### 例子

显示如何从其父节点获取给定子节点的索引。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

Body body = doc.FirstSection.Body;

// 检索第一节正文中最后一段的索引。
Assert.AreEqual(24, body.ChildNodes.IndexOf(body.LastParagraph));
```

### 也可以看看

* class [Node](../../node/)
* class [CompositeNode](../)
* 命名空间 [Aspose.Words](../../compositenode/)
* 部件 [Aspose.Words](../../../)


