---
title: DocumentProperty.Name
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentProperty propiedad. Devuelve el nombre de la propiedad.
type: docs
weight: 30
url: /es/net/aspose.words.properties/documentproperty/name/
---
## DocumentProperty.Name property

Devuelve el nombre de la propiedad.

```csharp
public string Name { get; }
```

### Observaciones

No puede ser nulo y no puede ser una cadena vacía.

### Ejemplos

Muestra cómo trabajar con propiedades de documentos integradas.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// El objeto "Documento" contiene algunos de sus metadatos en sus miembros.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// El documento también almacena metadatos en sus propiedades integradas.
// Cada propiedad incorporada es un miembro del objeto "BuiltInDocumentProperties" del documento.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // Algunas propiedades pueden almacenar varios valores.
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

### Ver también

* class [DocumentProperty](../)
* espacio de nombres [Aspose.Words.Properties](../../documentproperty/)
* asamblea [Aspose.Words](../../../)


