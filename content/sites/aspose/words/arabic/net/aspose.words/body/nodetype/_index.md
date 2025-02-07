---
title: Body.NodeType
second_title: Aspose.Words لمراجع .NET API
description: Body ملكية. عوائد NodeType. الجسم .
type: docs
weight: 20
url: /ar/net/aspose.words/body/nodetype/
---
## Body.NodeType property

عوائد **NodeType. الجسم** .

```csharp
public override NodeType NodeType { get; }
```

### أمثلة

يوضح كيفية التكرار من خلال العناصر الفرعية لعقدة مركبة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Primary header");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("Primary footer");

Section section = doc.FirstSection;

// A القسم هو عقدة مركبة ويمكن أن يحتوي على عقد فرعية ،
// ولكن فقط إذا كانت هذه العقد الفرعية من نوع العقدة "Body" أو "HeaderFooter".
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

### أنظر أيضا

* enum [NodeType](../../nodetype/)
* class [Body](../)
* مساحة الاسم [Aspose.Words](../../body/)
* المجسم [Aspose.Words](../../../)


