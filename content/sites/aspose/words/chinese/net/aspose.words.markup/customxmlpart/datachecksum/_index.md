---
title: CustomXmlPart.DataChecksum
second_title: Aspose.Words for .NET API 参考
description: CustomXmlPart 财产. 指定循环冗余校验 CRC 校验和Data内容.
type: docs
weight: 30
url: /zh/net/aspose.words.markup/customxmlpart/datachecksum/
---
## CustomXmlPart.DataChecksum property

指定循环冗余校验 (CRC) 校验和[`Data`](../data/)内容.

```csharp
public long DataChecksum { get; }
```

### 例子

显示如何在运行时计算校验和。

```csharp
Document doc = new Document();

StructuredDocumentTag richText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(richText);

// 校验和是只读的，使用对应的自定义 XML 数据部分的数据计算。
richText.XmlMapping.SetMapping(doc.CustomXmlParts.Add(Guid.NewGuid().ToString(),
    "<root><text>ContentControl</text></root>"), "/root/text", "");

long checksum = richText.XmlMapping.CustomXmlPart.DataChecksum;
Console.WriteLine(checksum);

richText.XmlMapping.SetMapping(doc.CustomXmlParts.Add(Guid.NewGuid().ToString(),
    "<root><text>Updated ContentControl</text></root>"), "/root/text", "");

long updatedChecksum = richText.XmlMapping.CustomXmlPart.DataChecksum;
Console.WriteLine(updatedChecksum);

// 我们更改了标签的 XmlPart，校验和在运行时更新。
Assert.AreNotEqual(checksum, updatedChecksum);
```

### 也可以看看

* class [CustomXmlPart](../)
* 命名空间 [Aspose.Words.Markup](../../customxmlpart/)
* 部件 [Aspose.Words](../../../)


