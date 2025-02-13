---
title: Node.CustomNodeId
second_title: Referencia de API de Aspose.Words para .NET
description: Node propiedad. Especifica el identificador de nodo personalizado.
type: docs
weight: 10
url: /es/net/aspose.words/node/customnodeid/
---
## Node.CustomNodeId property

Especifica el identificador de nodo personalizado.

```csharp
public int CustomNodeId { get; set; }
```

### Observaciones

El valor predeterminado es cero.

Este identificador se puede establecer y utilizar arbitrariamente. Por ejemplo, como clave para obtener datos externos.

Nota importante, el valor especificado no se guarda en un archivo de salida y existe solo durante la vida útil del nodo.

### Ejemplos

Muestra cómo recorrer la colección de nodos secundarios de un nodo compuesto.

```csharp
Document doc = new Document();

// Agregue dos carreras y una forma como nodos secundarios al primer párrafo de este documento.
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
paragraph.AppendChild(new Run(doc, "Hello world! "));

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
// Tenga en cuenta que el 'CustomNodeId' no se guarda en un archivo de salida y existe solo durante la vida útil del nodo.
shape.CustomNodeId = 100;
shape.WrapType = WrapType.Inline;
paragraph.AppendChild(shape);

paragraph.AppendChild(new Run(doc, "Hello again!"));

// Iterar a través de la colección de elementos secundarios inmediatos del párrafo,
// e imprima cualquier ejecución o forma que encontremos dentro.
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

### Ver también

* class [Node](../)
* espacio de nombres [Aspose.Words](../../node/)
* asamblea [Aspose.Words](../../../)


