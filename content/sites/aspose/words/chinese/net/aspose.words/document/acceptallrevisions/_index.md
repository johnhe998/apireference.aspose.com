---
title: Document.AcceptAllRevisions
second_title: Aspose.Words for .NET API 参考
description: Document 方法. 接受文档中的所有跟踪更改
type: docs
weight: 500
url: /zh/net/aspose.words/document/acceptallrevisions/
---
## Document.AcceptAllRevisions method

接受文档中的所有跟踪更改。

```csharp
public void AcceptAllRevisions()
```

### 评论

这个方法是一个捷径[`AcceptAll`](../../revisioncollection/acceptall/).

### 例子

显示如何接受文档中的所有跟踪更改。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 在跟踪更改的同时编辑文档以创建一些修订。
doc.StartTrackRevisions("John Doe");
builder.Write("Hello world! ");
builder.Write("Hello again! "); 
builder.Write("This is another revision.");
doc.StopTrackRevisions();

Assert.AreEqual(3, doc.Revisions.Count);

// 我们可以遍历每个修订并接受/拒绝它作为我们文档的一部分。
// 如果我们知道我们希望接受每个修订，我们可以通过调用此方法更直接地做到这一点。
doc.AcceptAllRevisions();

Assert.AreEqual(0, doc.Revisions.Count);
Assert.AreEqual("Hello world! Hello again! This is another revision.", doc.GetText().Trim());
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


