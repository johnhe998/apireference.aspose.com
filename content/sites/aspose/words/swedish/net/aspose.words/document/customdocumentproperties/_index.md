---
title: Document.CustomDocumentProperties
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Returnerar en samling som representerar alla anpassade dokumentegenskaper för dokumentet.
type: docs
weight: 70
url: /sv/net/aspose.words/document/customdocumentproperties/
---
## Document.CustomDocumentProperties property

Returnerar en samling som representerar alla anpassade dokumentegenskaper för dokumentet.

```csharp
public CustomDocumentProperties CustomDocumentProperties { get; }
```

### Exempel

Visar hur man arbetar med inbyggda dokumentegenskaper.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// "Dokument"-objektet innehåller en del av dess metadata i sina medlemmar.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// Dokumentet lagrar även metadata i sina inbyggda egenskaper.
// Varje inbyggd egenskap är en medlem av dokumentets "BuiltInDocumentProperties"-objekt.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // Vissa egenskaper kan lagra flera värden.
    if (docProperty.Value is ICollection<object>)
    {
        foreach (object value in docProperty.Value as ICollection<object>)
            Console.WriteLine($"\tValue:\t\"{value}\"");
    }
    else
    {
        Console.WriteLine($"\tValue:\t\"{docProperty.Value}\"");
    }
}
```

### Se även

* class [CustomDocumentProperties](../../../aspose.words.properties/customdocumentproperties/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


