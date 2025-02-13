---
title: Document.Frameset
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 返回一个Frameset例如如果此文档表示一个框架页面
type: docs
weight: 160
url: /zh/net/aspose.words/document/frameset/
---
## Document.Frameset property

返回一个`Frameset`例如，如果此文档表示一个框架页面。

```csharp
public Frameset Frameset { get; }
```

### 评论

如果文档没有加框，则属性有 **无效的**值.

### 例子

显示如何访问页面上的框架。

```csharp
// 文档包含多个带有指向其他文档的链接的框架。
Document doc = new Document(MyDir + "Frameset.docx");

// 我们可以检查默认 URL（网页 URL 或本地文档）或者框架是否是外部资源。
Assert.AreEqual("https://file-examples-com.github.io/uploads/2017/02/file-sample_100kB.docx",
    doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl);
Assert.True(doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile);

Assert.AreEqual("Document.docx", doc.Frameset.ChildFramesets[1].FrameDefaultUrl);
Assert.False(doc.Frameset.ChildFramesets[1].IsFrameLinkToFile);

// 更改我们其中一个框架的属性。
doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl =
    "https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Absolute%20position%20tab.docx";
doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile = false;
```

### 也可以看看

* class [Frameset](../../../aspose.words.framesets/frameset/)
* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


