---
title: Section.NodeType
second_title: Referencia de API de Aspose.Words para .NET
description: Section propiedad. Devoluciones NodeType.Sección .
type: docs
weight: 40
url: /es/net/aspose.words/section/nodetype/
---
## Section.NodeType property

Devoluciones **NodeType.Sección** .

```csharp
public override NodeType NodeType { get; }
```

### Ejemplos

Muestra cómo recorrer el árbol de nodos secundarios de un nodo compuesto.

```csharp
{
    Document doc = new Document(MyDir + "Paragraphs.docx");

    // Cualquier nodo que pueda contener nodos secundarios, como el propio documento, es compuesto.
    Assert.True(doc.IsComposite);

    // Invoque la función recursiva que pasará e imprimirá todos los nodos secundarios de un nodo compuesto.
    TraverseAllNodes(doc, 0);
}

/// <summary>
/// Recorre recursivamente un árbol de nodos mientras imprime el tipo de cada nodo
/// con una sangría que depende de la profundidad, así como del contenido de todos los nodos en línea.
/// </summary>
public void TraverseAllNodes(CompositeNode parentNode, int depth)
{
    for (Node childNode = parentNode.FirstChild; childNode != null; childNode = childNode.NextSibling)
    {
        Console.Write($"{new string('\t', depth)}{Node.NodeTypeToString(childNode.NodeType)}");

        // Recurre al nodo si es un nodo compuesto. De lo contrario, imprima su contenido si es un nodo en línea.
        if (childNode.IsComposite)
        {
            Console.WriteLine();
            TraverseAllNodes((CompositeNode)childNode, depth + 1);
        }
        else if (childNode is Inline)
        {
            Console.WriteLine($" - \"{childNode.GetText().Trim()}\"");
        }
        else
        {
            Console.WriteLine();
        }
    }
}
```

### Ver también

* enum [NodeType](../../nodetype/)
* class [Section](../)
* espacio de nombres [Aspose.Words](../../section/)
* asamblea [Aspose.Words](../../../)


