---
title: Document.Compliance
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 获取根据加载的文档内容确定的 OOXML 合规版本 仅对 OOXML 文档有意义
type: docs
weight: 60
url: /zh/net/aspose.words/document/compliance/
---
## Document.Compliance property

获取根据加载的文档内容确定的 OOXML 合规版本。 仅对 OOXML 文档有意义。

```csharp
public OoxmlCompliance Compliance { get; }
```

### 评论

如果您创建了一个新的空白文档或加载非 OOXML document 返回Ecma376_2006价值。

### 例子

显示如何读取已加载文档的 Open Office XML 合规性版本。

```csharp
// 不同版本的 Microsoft Word 创建的文档之间的合规版本不同。
Document doc = new Document(MyDir + "Document.doc");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Ecma376_2006);

doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Iso29500_2008_Transitional);
```

### 也可以看看

* enum [OoxmlCompliance](../../../aspose.words.saving/ooxmlcompliance/)
* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


