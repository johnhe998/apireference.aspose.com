---
title: StructuredDocumentTagRangeStart.IsShowingPlaceholderText
second_title: Aspose.Words for .NET API 参考
description: StructuredDocumentTagRangeStart 财产. 指定此结构化文档标记的内容是否应解释为包含 占位符文本与结构化文档标记中的常规文本内容相反
type: docs
weight: 50
url: /zh/net/aspose.words.markup/structureddocumenttagrangestart/isshowingplaceholdertext/
---
## StructuredDocumentTagRangeStart.IsShowingPlaceholderText property

指定此结构化文档标记的内容是否应解释为包含 占位符文本（与结构化文档标记中的常规文本内容相反）。

如果设置为 true，则在打开此文档时应恢复此状态（显示占位符文本）。

```csharp
public bool IsShowingPlaceholderText { get; set; }
```

### 例子

显示如何获取多节结构化文档标签的属性。

```csharp
Document doc = new Document(MyDir + "Multi-section structured document tags.docx");

StructuredDocumentTagRangeStart rangeStartTag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true)[0] as StructuredDocumentTagRangeStart;
StructuredDocumentTagRangeEnd rangeEndTag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeEnd, true)[0] as StructuredDocumentTagRangeEnd;

Console.WriteLine("StructuredDocumentTagRangeStart values:");
Console.WriteLine($"\t|Id: {rangeStartTag.Id}");
Console.WriteLine($"\t|Title: {rangeStartTag.Title}");
Console.WriteLine($"\t|PlaceholderName: {rangeStartTag.PlaceholderName}");
Console.WriteLine($"\t|IsShowingPlaceholderText: {rangeStartTag.IsShowingPlaceholderText}");
Console.WriteLine($"\t|LockContentControl: {rangeStartTag.LockContentControl}");
Console.WriteLine($"\t|LockContents: {rangeStartTag.LockContents}");
Console.WriteLine($"\t|Level: {rangeStartTag.Level}");
Console.WriteLine($"\t|NodeType: {rangeStartTag.NodeType}");
Console.WriteLine($"\t|RangeEnd: {rangeStartTag.RangeEnd}");
Console.WriteLine($"\t|Color: {rangeStartTag.Color.ToArgb()}");
Console.WriteLine($"\t|SdtType: {rangeStartTag.SdtType}");
Console.WriteLine($"\t|FlatOpcContent: {rangeStartTag.WordOpenXML}");
Console.WriteLine($"\t|Tag: {rangeStartTag.Tag}\n");

Console.WriteLine("StructuredDocumentTagRangeEnd values:");
Console.WriteLine($"\t|Id: {rangeEndTag.Id}");
Console.WriteLine($"\t|NodeType: {rangeEndTag.NodeType}");
```

### 也可以看看

* class [StructuredDocumentTagRangeStart](../)
* 命名空间 [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* 部件 [Aspose.Words](../../../)


