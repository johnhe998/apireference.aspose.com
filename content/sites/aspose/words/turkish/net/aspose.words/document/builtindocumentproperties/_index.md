---
title: Document.BuiltInDocumentProperties
second_title: Aspose.Words for .NET API Referansı
description: Document mülk. Belgenin tüm yerleşik belge özelliklerini temsil eden bir koleksiyon döndürür.
type: docs
weight: 40
url: /tr/net/aspose.words/document/builtindocumentproperties/
---
## Document.BuiltInDocumentProperties property

Belgenin tüm yerleşik belge özelliklerini temsil eden bir koleksiyon döndürür.

```csharp
public BuiltInDocumentProperties BuiltInDocumentProperties { get; }
```

### Örnekler

Yerleşik belge özellikleriyle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// "Belge" nesnesi, meta verilerinin bir kısmını üyelerinde içerir.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// Belge ayrıca meta verileri yerleşik özelliklerinde de saklar.
// Her yerleşik özellik, belgenin "BuiltInDocumentProperties" nesnesinin bir üyesidir.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // Bazı özellikler birden fazla değer depolayabilir.
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

### Ayrıca bakınız

* class [BuiltInDocumentProperties](../../../aspose.words.properties/builtindocumentproperties/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


