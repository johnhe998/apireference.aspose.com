---
title: Body.NodeType
second_title: Aspose.Words för .NET API Referens
description: Body fast egendom. Returnerar NodeType.Body .
type: docs
weight: 20
url: /sv/net/aspose.words/body/nodetype/
---
## Body.NodeType property

Returnerar **NodeType.Body** .

```csharp
public override NodeType NodeType { get; }
```

### Exempel

Visar hur man itererar genom barnen i en sammansatt nod.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Primary header");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("Primary footer");

Section section = doc.FirstSection;

// En sektion är en sammansatt nod och kan innehålla underordnade noder,
// men bara om de underordnade noderna är av nodtypen "Body" eller "HeaderFooter".
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

### Se även

* enum [NodeType](../../nodetype/)
* class [Body](../)
* namnutrymme [Aspose.Words](../../body/)
* hopsättning [Aspose.Words](../../../)


