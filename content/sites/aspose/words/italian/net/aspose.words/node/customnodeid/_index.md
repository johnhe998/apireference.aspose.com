---
title: Node.CustomNodeId
second_title: Aspose.Words per .NET API Reference
description: Node proprietà. Specifica lidentificatore del nodo personalizzato.
type: docs
weight: 10
url: /it/net/aspose.words/node/customnodeid/
---
## Node.CustomNodeId property

Specifica l'identificatore del nodo personalizzato.

```csharp
public int CustomNodeId { get; set; }
```

### Osservazioni

Il valore predefinito è zero.

Questo identificatore può essere impostato e utilizzato arbitrariamente. Ad esempio, come chiave per ottenere dati esterni.

Nota importante, il valore specificato non viene salvato in un file di output ed esiste solo durante la vita del nodo.

### Esempi

Mostra come attraversare la raccolta di nodi figlio di un nodo composito.

```csharp
Document doc = new Document();

// Aggiungi due esecuzioni e una forma come nodi figlio al primo paragrafo di questo documento.
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
paragraph.AppendChild(new Run(doc, "Hello world! "));

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
// Nota che 'CustomNodeId' non viene salvato in un file di output ed esiste solo durante la vita del nodo.
shape.CustomNodeId = 100;
shape.WrapType = WrapType.Inline;
paragraph.AppendChild(shape);

paragraph.AppendChild(new Run(doc, "Hello again!"));

// Scorri la raccolta del paragrafo dei figli immediati,
// e stampa qualsiasi traccia o forma che troviamo all'interno.
NodeCollection children = paragraph.ChildNodes;

Assert.AreEqual(3, paragraph.ChildNodes.Count);

foreach (Node child in children)
    switch (child.NodeType)
    {
        case NodeType.Run:
            Console.WriteLine("Run contents:");
            Console.WriteLine($"\t\"{child.GetText().Trim()}\"");
            break;
        case NodeType.Shape:
            Shape childShape = (Shape)child;
            Console.WriteLine("Shape:");
            Console.WriteLine($"\t{childShape.ShapeType}, {childShape.Width}x{childShape.Height}");
    }
```

### Guarda anche

* class [Node](../)
* spazio dei nomi [Aspose.Words](../../node/)
* assemblea [Aspose.Words](../../../)


