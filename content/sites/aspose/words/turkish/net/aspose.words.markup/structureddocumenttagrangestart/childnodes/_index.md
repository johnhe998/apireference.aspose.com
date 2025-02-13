---
title: StructuredDocumentTagRangeStart.ChildNodes
second_title: Aspose.Words for .NET API Referansı
description: StructuredDocumentTagRangeStart mülk. Bu aralık başlangıç düğümü ile aralık bitiş düğümü arasındaki tüm düğümleri alır.
type: docs
weight: 20
url: /tr/net/aspose.words.markup/structureddocumenttagrangestart/childnodes/
---
## StructuredDocumentTagRangeStart.ChildNodes property

Bu aralık başlangıç düğümü ile aralık bitiş düğümü arasındaki tüm düğümleri alır.

```csharp
public NodeCollection ChildNodes { get; }
```

### Örnekler

StructuredDocumentTagRangeStart alt düğümlerinin nasıl alınacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Multi-section structured document tags.docx");
StructuredDocumentTagRangeStart tag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true)[0] as StructuredDocumentTagRangeStart;

Console.WriteLine("StructuredDocumentTagRangeStart values:");
Console.WriteLine($"\t|Child nodes count: {tag.ChildNodes.Count}\n");

foreach (Node node in tag.ChildNodes)
    Console.WriteLine($"\t|Child node type: {node.NodeType}");

foreach (Node node in tag.GetChildNodes(NodeType.Run, true))
    Console.WriteLine($"\t|Child node text: {node.GetText()}");
```

### Ayrıca bakınız

* class [NodeCollection](../../../aspose.words/nodecollection/)
* class [StructuredDocumentTagRangeStart](../)
* ad alanı [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* toplantı [Aspose.Words](../../../)


