---
title: Document.VersionsCount
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 获取存储在 DOC 文档中的文档版本数
type: docs
weight: 440
url: /zh/net/aspose.words/document/versionscount/
---
## Document.VersionsCount property

获取存储在 DOC 文档中的文档版本数。

```csharp
public int VersionsCount { get; }
```

### 评论

Microsoft Word 中的版本可通过文件/版本菜单访问。 Microsoft Word 仅支持 DOC 文件的 版本。

此属性允许检测在 Aspose.Words 中打开此 document 之前是否存储了文档版本。 Aspose.Words 不提供对文档版本的其他支持。 如果您使用 Aspose.Words 保存此文档，则保存的文档将不包含版本。

### 例子

展示如何使用旧版 Microsoft Word 文档的版本计数功能。

```csharp
Document doc = new Document(MyDir + "Versions.doc");

// 我们可以读取文档的这个属性，但是我们不能在保存时保存它。
Assert.AreEqual(4, doc.VersionsCount);

doc.Save(ArtifactsDir + "Document.VersionsCount.doc");      
doc = new Document(ArtifactsDir + "Document.VersionsCount.doc");

Assert.AreEqual(0, doc.VersionsCount);
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


