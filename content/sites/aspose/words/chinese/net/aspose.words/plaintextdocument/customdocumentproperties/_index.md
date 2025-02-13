---
title: PlainTextDocument.CustomDocumentProperties
second_title: Aspose.Words for .NET API 参考
description: PlainTextDocument 财产. 获取CustomDocumentProperties文件的.
type: docs
weight: 30
url: /zh/net/aspose.words/plaintextdocument/customdocumentproperties/
---
## PlainTextDocument.CustomDocumentProperties property

获取`CustomDocumentProperties`文件的.

```csharp
public CustomDocumentProperties CustomDocumentProperties { get; }
```

### 例子

演示如何以纯文本形式加载 Microsoft Word 文档的内容，然后访问原始文档的自定义属性。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
doc.CustomDocumentProperties.Add("Location of writing", "123 Main St, London, UK");

doc.Save(ArtifactsDir + "PlainTextDocument.CustomDocumentProperties.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.CustomDocumentProperties.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
Assert.AreEqual("123 Main St, London, UK", plaintext.CustomDocumentProperties["Location of writing"].Value);
```

### 也可以看看

* class [CustomDocumentProperties](../../../aspose.words.properties/customdocumentproperties/)
* class [PlainTextDocument](../)
* 命名空间 [Aspose.Words](../../plaintextdocument/)
* 部件 [Aspose.Words](../../../)


