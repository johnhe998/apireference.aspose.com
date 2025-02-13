---
title: Class CustomPartCollection
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Markup.CustomPartCollection clase. Representa una colección deCustomPart objetos.
type: docs
weight: 3670
url: /es/net/aspose.words.markup/custompartcollection/
---
## CustomPartCollection class

Representa una colección de[`CustomPart`](../custompart/) objetos.

```csharp
public class CustomPartCollection : IEnumerable<CustomPart>
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [CustomPartCollection](custompartcollection/)() | Constructor predeterminado |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Count](../../aspose.words.markup/custompartcollection/count/) { get; } | Obtiene el número de elementos que contiene la colección. |
| [Item](../../aspose.words.markup/custompartcollection/item/) { get; set; } | Obtiene o establece un elemento en el índice especificado. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [Add](../../aspose.words.markup/custompartcollection/add/)(CustomPart) | Agrega un elemento a la colección. |
| [Clear](../../aspose.words.markup/custompartcollection/clear/)() | Elimina todos los elementos de la colección. |
| [Clone](../../aspose.words.markup/custompartcollection/clone/)() | Hace una copia profunda de esta colección y sus elementos. |
| [GetEnumerator](../../aspose.words.markup/custompartcollection/getenumerator/)() | Devuelve un objeto enumerador que se puede usar para iterar sobre todos los elementos de la colección. |
| [RemoveAt](../../aspose.words.markup/custompartcollection/removeat/)(int) | Elimina un elemento en el índice especificado. |

### Observaciones

Normalmente no necesita crear instancias de esta clase. Accede a piezas personalizadas relacionadas con el paquete OOXML a través de[`PackageCustomParts`](../../aspose.words/document/packagecustomparts/) propiedad.

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

* class [CustomPart](../custompart/)
* espacio de nombres [Aspose.Words.Markup](../../aspose.words.markup/)
* asamblea [Aspose.Words](../../)


