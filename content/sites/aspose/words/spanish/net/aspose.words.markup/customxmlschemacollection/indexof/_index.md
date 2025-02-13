---
title: CustomXmlSchemaCollection.IndexOf
second_title: Referencia de API de Aspose.Words para .NET
description: CustomXmlSchemaCollection método. Devuelve el índice basado en cero del valor especificado en la colección.
type: docs
weight: 70
url: /es/net/aspose.words.markup/customxmlschemacollection/indexof/
---
## CustomXmlSchemaCollection.IndexOf method

Devuelve el índice basado en cero del valor especificado en la colección.

```csharp
public int IndexOf(string value)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| value | String | El valor que distingue entre mayúsculas y minúsculas para localizar. |

### Valor_devuelto

El índice de base cero. Valor negativo si no se encuentra.

### Ejemplos

Muestra cómo trabajar con una colección de esquemas XML.

```csharp
Document doc = new Document();

string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello, World!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

// Agregar una asociación de esquema XML.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// Clonar la colección de asociaciones de esquemas XML de la parte XML personalizada,
// y luego agregue un par de esquemas nuevos al clon.
CustomXmlSchemaCollection schemas = xmlPart.Schemas.Clone();
schemas.Add("http://www.w3.org/2001/XMLSchema-instance");
schemas.Add("http://schemas.microsoft.com/office/2006/metadata/contentType");

Assert.AreEqual(3, schemas.Count);
Assert.AreEqual(2, schemas.IndexOf("http://schemas.microsoft.com/office/2006/metadata/contentType"));

// Enumerar los esquemas e imprimir cada elemento.
using (IEnumerator<string> enumerator = schemas.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine(enumerator.Current);
}

// A continuación se muestran tres formas de eliminar esquemas de la colección.
// 1 - Eliminar un esquema por índice:
schemas.RemoveAt(2);

// 2 - Eliminar un esquema por valor:
schemas.Remove("http://www.w3.org/2001/XMLSchema");

// 3 - Usa el método "Borrar" para vaciar la colección de una vez.
schemas.Clear();

Assert.AreEqual(0, schemas.Count);
```

### Ver también

* class [CustomXmlSchemaCollection](../)
* espacio de nombres [Aspose.Words.Markup](../../customxmlschemacollection/)
* asamblea [Aspose.Words](../../../)


