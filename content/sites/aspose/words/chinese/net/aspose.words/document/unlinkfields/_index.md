---
title: Document.UnlinkFields
second_title: Aspose.Words for .NET API 参考
description: Document 方法. 取消链接整个文档中的字段
type: docs
weight: 710
url: /zh/net/aspose.words/document/unlinkfields/
---
## Document.UnlinkFields method

取消链接整个文档中的字段。

```csharp
public void UnlinkFields()
```

### 评论

将整个文档中的所有字段替换为其最新结果。

要取消链接文档特定部分中的字段，请使用[`UnlinkFields`](../../range/unlinkfields/).

### 例子

显示如何取消链接文档中的所有字段。

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");

doc.UnlinkFields();
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


