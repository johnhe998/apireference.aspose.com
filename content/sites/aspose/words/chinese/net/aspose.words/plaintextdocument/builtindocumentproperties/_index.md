---
title: PlainTextDocument.BuiltInDocumentProperties
second_title: Aspose.Words for .NET API 参考
description: PlainTextDocument 财产. 获取BuiltInDocumentProperties文件的.
type: docs
weight: 20
url: /zh/net/aspose.words/plaintextdocument/builtindocumentproperties/
---
## PlainTextDocument.BuiltInDocumentProperties property

获取`BuiltInDocumentProperties`文件的.

```csharp
public BuiltInDocumentProperties BuiltInDocumentProperties { get; }
```

### 例子

演示如何以纯文本形式加载 Microsoft Word 文档的内容，然后访问原始文档的内置属性。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
doc.BuiltInDocumentProperties.Author = "John Doe";

doc.Save(ArtifactsDir + "PlainTextDocument.BuiltInProperties.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.BuiltInProperties.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
Assert.AreEqual("John Doe", plaintext.BuiltInDocumentProperties.Author);
```

### 也可以看看

* class [BuiltInDocumentProperties](../../../aspose.words.properties/builtindocumentproperties/)
* class [PlainTextDocument](../)
* 命名空间 [Aspose.Words](../../plaintextdocument/)
* 部件 [Aspose.Words](../../../)


