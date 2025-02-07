---
title: Body.NodeType
second_title: Aspose.Words per .NET API Reference
description: Body proprietà. Restituisce NodeType.Body .
type: docs
weight: 20
url: /it/net/aspose.words/body/nodetype/
---
## Body.NodeType property

Restituisce **NodeType.Body** .

```csharp
public override NodeType NodeType { get; }
```

### Esempi

Mostra come scorrere i figli di un nodo composto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Primary header");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("Primary footer");

Section section = doc.FirstSection;

// Una sezione è un nodo composito e può contenere nodi figli,
// ma solo se quei nodi figlio sono di tipo "Body" o "HeaderFooter".
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

### Guarda anche

* enum [NodeType](../../nodetype/)
* class [Body](../)
* spazio dei nomi [Aspose.Words](../../body/)
* assemblea [Aspose.Words](../../../)


