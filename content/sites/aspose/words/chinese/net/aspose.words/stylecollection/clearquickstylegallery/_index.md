---
title: StyleCollection.ClearQuickStyleGallery
second_title: Aspose.Words for .NET API 参考
description: StyleCollection 方法. 从快速样式库面板中删除所有样式
type: docs
weight: 80
url: /zh/net/aspose.words/stylecollection/clearquickstylegallery/
---
## StyleCollection.ClearQuickStyleGallery method

从“快速样式库”面板中删除所有样式。

```csharp
public void ClearQuickStyleGallery()
```

### 例子

显示如何从样式库面板中删除样式。

```csharp
Document doc = new Document();

// 请注意，删除样式目前仅适用于 DOCX 格式。
doc.Styles.ClearQuickStyleGallery();

doc.Save(ArtifactsDir + "Styles.RemoveStylesFromStyleGallery.docx");
```

### 也可以看看

* class [StyleCollection](../)
* 命名空间 [Aspose.Words](../../stylecollection/)
* 部件 [Aspose.Words](../../../)


