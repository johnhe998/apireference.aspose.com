---
title: HeaderFooter.NodeType
second_title: Aspose.Words per .NET API Reference
description: HeaderFooter proprietà. Restituisce NodeType.HeaderFooter .
type: docs
weight: 50
url: /it/net/aspose.words/headerfooter/nodetype/
---
## HeaderFooter.NodeType property

Restituisce **NodeType.HeaderFooter** .

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
* class [HeaderFooter](../)
* spazio dei nomi [Aspose.Words](../../headerfooter/)
* assemblea [Aspose.Words](../../../)


