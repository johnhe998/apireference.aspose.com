---
title: DocumentProperty.LinkSource
second_title: Aspose.Words for .NET API 参考
description: DocumentProperty 财产. 获取链接的自定义文档属性的来源
type: docs
weight: 20
url: /zh/net/aspose.words.properties/documentproperty/linksource/
---
## DocumentProperty.LinkSource property

获取链接的自定义文档属性的来源。

```csharp
public string LinkSource { get; }
```

### 例子

显示如何将自定义文档属性链接到书签。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("MyBookmark");
builder.Write("Hello world!");
builder.EndBookmark("MyBookmark");

// 将新的自定义属性链接到书签。该物业的价值
// 将是它在“LinkSource”成员中引用的书签的内容。
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");

Assert.AreEqual(true, customProperty.IsLinkToContent);
Assert.AreEqual("MyBookmark", customProperty.LinkSource);
Assert.AreEqual("Hello world!", customProperty.Value);

doc.Save(ArtifactsDir + "DocumentProperties.LinkCustomDocumentPropertiesToBookmark.docx");
```

### 也可以看看

* class [DocumentProperty](../)
* 命名空间 [Aspose.Words.Properties](../../documentproperty/)
* 部件 [Aspose.Words](../../../)


