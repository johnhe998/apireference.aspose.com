---
title: BuiltInDocumentProperties.HyperlinkBase
second_title: Aspose.Words for .NET API 参考
description: BuiltInDocumentProperties 财产. 指定用于评估本文档中的相对超链接的基本字符串
type: docs
weight: 120
url: /zh/net/aspose.words.properties/builtindocumentproperties/hyperlinkbase/
---
## BuiltInDocumentProperties.HyperlinkBase property

指定用于评估本文档中的相对超链接的基本字符串。

```csharp
public string HyperlinkBase { get; set; }
```

### 评论

Aspose.Words 不使用此属性。

### 例子

显示如何将超链接的基本部分存储在文档的属性中。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入指向本地文件系统中名为“Document.docx”的文档的相对超链接。
// 单击 Microsoft Word 中的链接将打开指定的文档（如果可用）。
builder.InsertHyperlink("Relative hyperlink", "Document.docx", false);

// 这个链接是相对的。如果同一文件夹中没有“Document.docx”
// 作为包含此链接的文档，链接将被破坏。
Assert.False(File.Exists(ArtifactsDir + "Document.docx"));
doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.BrokenLink.docx");

// 我们尝试链接到的文档与我们计划保存文档的目录不同。
// 我们可以通过在每个链接中放置一个绝对文件名来修复这样的链接。 
// 或者，我们可以提供一个基本链接，每个超链接都有一个相对文件名
// 当我们点击它时，它将添加到它的链接。 
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;
properties.HyperlinkBase = MyDir;

Assert.True(File.Exists(properties.HyperlinkBase + ((FieldHyperlink)doc.Range.Fields[0]).Address));

doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.WorkingLink.docx");
```

### 也可以看看

* class [BuiltInDocumentProperties](../)
* 命名空间 [Aspose.Words.Properties](../../builtindocumentproperties/)
* 部件 [Aspose.Words](../../../)


