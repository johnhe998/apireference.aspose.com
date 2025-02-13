---
title: CompositeNode.SelectNodes
second_title: Referencia de API de Aspose.Words para .NET
description: CompositeNode método. Selecciona una lista de nodos que coinciden con la expresión XPath.
type: docs
weight: 200
url: /es/net/aspose.words/compositenode/selectnodes/
---
## CompositeNode.SelectNodes method

Selecciona una lista de nodos que coinciden con la expresión XPath.

```csharp
public NodeList SelectNodes(string xpath)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| xpath | String | La expresión XPath. |

### Valor_devuelto

Una lista de nodos que coinciden con la consulta XPath.

### Observaciones

Por el momento, solo se admiten expresiones con nombres de elementos. No se admiten las expresiones que usan nombres de atributos.

### Ejemplos

Muestra cómo usar una expresión XPath para probar si un nodo está dentro de un campo.

```csharp
Document doc = new Document(MyDir + "Mail merge destination - Northwind employees.docx");

// La lista de nodos que resulta de esta expresión XPath contendrá todos los nodos que encontremos dentro de un campo.
// Sin embargo, los nodos FieldStart y FieldEnd pueden estar en la lista si hay campos anidados en la ruta.
// Actualmente no encuentra campos raros en los que FieldCode o FieldResult abarquen varios párrafos.
NodeList resultList =
    doc.SelectNodes("//FieldStart/siguiente-hermano::nodo()[siguiente-hermano::FieldField]");

// Comprueba si la ejecución especificada es uno de los nodos que están dentro del campo.
Console.WriteLine($"Contents of the first Run node that's part of a field: {resultList.First(n => n.NodeType == NodeType.Run).GetText().Trim()}");
```

Muestra cómo seleccionar determinados nodos mediante una expresión XPath.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Esta expresión extraerá todos los nodos de párrafo,
// que son descendientes de cualquier nodo de tabla en el documento.
NodeList nodeList = doc.SelectNodes("//Tabla//Párrafo");

// Iterar a través de la lista con un enumerador e imprimir el contenido de cada párrafo en cada celda de la tabla.
int index = 0;

using (IEnumerator<Node> e = nodeList.GetEnumerator())
    while (e.MoveNext())
        Console.WriteLine($"Table paragraph index {index++}, contents: \"{e.Current.GetText().Trim()}\"");

// Esta expresión seleccionará cualquier párrafo que sea hijo directo de cualquier nodo Cuerpo del documento.
nodeList = doc.SelectNodes("//Cuerpo del párrafo");

// Podemos tratar la lista como una matriz.
Assert.AreEqual(4, nodeList.ToArray().Length);

// Use SelectSingleNode para seleccionar el primer resultado de la misma expresión anterior.
Node node = doc.SelectSingleNode("//Cuerpo del párrafo");

Assert.AreEqual(typeof(Paragraph), node.GetType());
```

### Ver también

* class [NodeList](../../nodelist/)
* class [CompositeNode](../)
* espacio de nombres [Aspose.Words](../../compositenode/)
* asamblea [Aspose.Words](../../../)


