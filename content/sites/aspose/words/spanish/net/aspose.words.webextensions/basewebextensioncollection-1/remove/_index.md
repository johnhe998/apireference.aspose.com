---
title: BaseWebExtensionCollection1.Remove
second_title: Referencia de API de Aspose.Words para .NET
description: BaseWebExtensionCollection método. Elimina el elemento en el índice especificado de la colección.
type: docs
weight: 60
url: /es/net/aspose.words.webextensions/basewebextensioncollection-1/remove/
---
## BaseWebExtensionCollection&lt;T&gt;.Remove method

Elimina el elemento en el índice especificado de la colección.

```csharp
public void Remove(int index)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| index | Int32 | El índice de base cero del elemento de colección. |

### Ejemplos

Muestra cómo trabajar con la colección de extensiones web de un documento.

```csharp
Document doc = new Document(MyDir + "Web extension.docx");

Assert.AreEqual(1, doc.WebExtensionTaskPanes.Count);

// Imprime todas las propiedades de la extensión web del documento.
WebExtensionPropertyCollection webExtensionPropertyCollection = doc.WebExtensionTaskPanes[0].WebExtension.Properties;
using (IEnumerator<WebExtensionProperty> enumerator = webExtensionPropertyCollection.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        WebExtensionProperty webExtensionProperty = enumerator.Current;
        Console.WriteLine($"Binding name: {webExtensionProperty.Name}; Binding value: {webExtensionProperty.Value}");
    }
}

// Eliminar la extensión web.
doc.WebExtensionTaskPanes.Remove(0);

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Ver también

* class [BaseWebExtensionCollection&lt;T&gt;](../)
* espacio de nombres [Aspose.Words.WebExtensions](../../basewebextensioncollection-1/)
* asamblea [Aspose.Words](../../../)


