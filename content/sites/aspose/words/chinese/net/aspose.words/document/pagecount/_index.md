---
title: Document.PageCount
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 获取由最近的页面布局操作计算的文档中的页数
type: docs
weight: 300
url: /zh/net/aspose.words/document/pagecount/
---
## Document.PageCount property

获取由最近的页面布局操作计算的文档中的页数。

```csharp
public int PageCount { get; }
```

### 例子

显示如何计算文档中的页数。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Page 2");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Page 3");

// 验证文档的预期页数。
Assert.AreEqual(3, doc.PageCount);

// 获取 PageCount 属性调用文档的页面布局来计算值。
// 将文档渲染成固定的页面保存格式时，不需要重新做这个操作，
// 例如.pdf。因此，您可以节省一些时间，尤其是处理更复杂的文档。
doc.Save(ArtifactsDir + "Document.GetPageCount.pdf");
```

### 也可以看看

* method [UpdatePageLayout](../updatepagelayout/)
* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


