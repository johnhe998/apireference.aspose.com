---
title: CustomPart.Name
second_title: Referencia de API de Aspose.Words para .NET
description: CustomPart propiedad. Obtiene o establece el nombre absoluto de esta parte dentro del paquete OOXML o la URL de destino.
type: docs
weight: 50
url: /es/net/aspose.words.markup/custompart/name/
---
## CustomPart.Name property

Obtiene o establece el nombre absoluto de esta parte dentro del paquete OOXML o la URL de destino.

```csharp
public string Name { get; set; }
```

### Observaciones

Si el destino de la relación es interno, esta propiedad es el nombre absoluto de la parte dentro del paquete. Si el destino de la relación es externo, esta propiedad es la URL de destino.

El valor predeterminado es una cadena vacía. Un valor válido debe ser una cadena no vacía.

### Ejemplos

Muestra cómo acceder a la colección de piezas personalizadas arbitrarias de un documento.

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// Clona la segunda parte, luego agrega el clon a la colección.
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// Enumerar sobre la colección e imprimir cada parte.
using (IEnumerator<CustomPart> enumerator = doc.PackageCustomParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Part index {index}:");
        Console.WriteLine($"\tName:\t\t\t\t{enumerator.Current.Name}");
        Console.WriteLine($"\tContent type:\t\t{enumerator.Current.ContentType}");
        Console.WriteLine($"\tRelationship type:\t{enumerator.Current.RelationshipType}");
        Console.WriteLine(enumerator.Current.IsExternal ?
            "\tSourced from outside the document" :
            $"\tStored within the document, length: {enumerator.Current.Data.Length} bytes");
        index++;
    }
}

// Podemos eliminar elementos de esta colección individualmente o todos a la vez.
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### Ver también

* class [CustomPart](../)
* espacio de nombres [Aspose.Words.Markup](../../custompart/)
* asamblea [Aspose.Words](../../../)


