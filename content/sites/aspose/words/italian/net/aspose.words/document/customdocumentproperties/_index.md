---
title: Document.CustomDocumentProperties
second_title: Aspose.Words per .NET API Reference
description: Document proprietà. Restituisce una raccolta che rappresenta tutte le proprietà del documento personalizzate del documento.
type: docs
weight: 70
url: /it/net/aspose.words/document/customdocumentproperties/
---
## Document.CustomDocumentProperties property

Restituisce una raccolta che rappresenta tutte le proprietà del documento personalizzate del documento.

```csharp
public CustomDocumentProperties CustomDocumentProperties { get; }
```

### Esempi

Mostra come lavorare con le proprietà del documento integrate.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// L'oggetto "Documento" contiene alcuni dei suoi metadati nei suoi membri.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// Il documento memorizza anche i metadati nelle sue proprietà integrate.
// Ogni proprietà incorporata è un membro dell'oggetto "BuiltInDocumentProperties" del documento.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // Alcune proprietà possono memorizzare più valori.
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

### Guarda anche

* class [CustomDocumentProperties](../../../aspose.words.properties/customdocumentproperties/)
* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


