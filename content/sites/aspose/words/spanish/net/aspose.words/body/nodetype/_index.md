---
title: Body.NodeType
second_title: Referencia de API de Aspose.Words para .NET
description: Body propiedad. Devoluciones Tipo de nodo.Cuerpo .
type: docs
weight: 20
url: /es/net/aspose.words/body/nodetype/
---
## Body.NodeType property

Devoluciones **Tipo de nodo.Cuerpo** .

```csharp
public override NodeType NodeType { get; }
```

### Ejemplos

Muestra cómo iterar a través de los elementos secundarios de un nodo compuesto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Primary header");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("Primary footer");

Section section = doc.FirstSection;

// Una Sección es un nodo compuesto y puede contener nodos secundarios,
// pero solo si esos nodos secundarios son del tipo de nodo "Body" o "HeaderFooter".
foreach (Node node in section)
{
    switch (node.NodeType)
    {
        case NodeType.Body:
        {
            Body body = (Body)node;

            Console.WriteLine("Body:");
            Console.WriteLine($"\t\"{body.GetText().Trim()}\"");
            break;
        }
        case NodeType.HeaderFooter:
        {
            HeaderFooter headerFooter = (HeaderFooter)node;

            Console.WriteLine($"HeaderFooter type: {headerFooter.HeaderFooterType}:");
            Console.WriteLine($"\t\"{headerFooter.GetText().Trim()}\"");
            break;
        }
        default:
        {
            throw new Exception("Unexpected node type in a section.");
        }
    }
}
```

### Ver también

* enum [NodeType](../../nodetype/)
* class [Body](../)
* espacio de nombres [Aspose.Words](../../body/)
* asamblea [Aspose.Words](../../../)


