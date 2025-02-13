---
title: StructuredDocumentTagRangeStart.ChildNodes
second_title: Aspose.Words för .NET API Referens
description: StructuredDocumentTagRangeStart fast egendom. Hämtar alla noder mellan denna intervallstartnod och intervallslutnoden.
type: docs
weight: 20
url: /sv/net/aspose.words.markup/structureddocumenttagrangestart/childnodes/
---
## StructuredDocumentTagRangeStart.ChildNodes property

Hämtar alla noder mellan denna intervallstartnod och intervallslutnoden.

```csharp
public NodeCollection ChildNodes { get; }
```

### Exempel

Visar hur man får barnnoder för StructuredDocumentTagRangeStart.

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

### Se även

* class [NodeCollection](../../../aspose.words/nodecollection/)
* class [StructuredDocumentTagRangeStart](../)
* namnutrymme [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* hopsättning [Aspose.Words](../../../)


