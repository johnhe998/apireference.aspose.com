---
title: StructuredDocumentTagRangeStart.ChildNodes
second_title: Referencia de API de Aspose.Words para .NET
description: StructuredDocumentTagRangeStart propiedad. Obtiene todos los nodos entre este nodo inicial de rango y el nodo final de rango.
type: docs
weight: 20
url: /es/net/aspose.words.markup/structureddocumenttagrangestart/childnodes/
---
## StructuredDocumentTagRangeStart.ChildNodes property

Obtiene todos los nodos entre este nodo inicial de rango y el nodo final de rango.

```csharp
public NodeCollection ChildNodes { get; }
```

### Ejemplos

Muestra cómo obtener nodos secundarios de StructuredDocumentTagRangeStart.

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

### Ver también

* class [NodeCollection](../../../aspose.words/nodecollection/)
* class [StructuredDocumentTagRangeStart](../)
* espacio de nombres [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* asamblea [Aspose.Words](../../../)


