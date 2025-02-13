---
title: StructuredDocumentTag.WordOpenXML
second_title: Aspose.Words for .NET API 参考
description: StructuredDocumentTag 财产. 获取一个字符串该字符串表示包含在FlatOpc格式.
type: docs
weight: 300
url: /zh/net/aspose.words.markup/structureddocumenttag/wordopenxml/
---
## StructuredDocumentTag.WordOpenXML property

获取一个字符串，该字符串表示包含在FlatOpc格式.

```csharp
public string WordOpenXML { get; }
```

### 例子

显示如何获取包含在 FlatOpc 格式的节点中的 XML。

```csharp
Document doc = new Document(MyDir + "Structured document tags.docx");

List<StructuredDocumentTag> tags = doc.GetChildNodes(NodeType.StructuredDocumentTag, true)
    .OfType<StructuredDocumentTag>().ToList();

Assert.True(tags[0].WordOpenXML
    .Contains(
        "<pkg:part pkg:name=\"/docProps/app.xml\" pkg:contentType=\"application/vnd.openxmlformats-officedocument.extended-properties+xml\">"));
```

### 也可以看看

* class [StructuredDocumentTag](../)
* 命名空间 [Aspose.Words.Markup](../../structureddocumenttag/)
* 部件 [Aspose.Words](../../../)


