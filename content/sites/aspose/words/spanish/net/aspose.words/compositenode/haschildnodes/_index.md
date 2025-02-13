---
title: CompositeNode.HasChildNodes
second_title: Referencia de API de Aspose.Words para .NET
description: CompositeNode propiedad. Devuelve verdadero si este nodo tiene nodos secundarios.
type: docs
weight: 40
url: /es/net/aspose.words/compositenode/haschildnodes/
---
## CompositeNode.HasChildNodes property

Devuelve verdadero si este nodo tiene nodos secundarios.

```csharp
public bool HasChildNodes { get; }
```

### Ejemplos

Muestra cómo combinar las filas de dos tablas en una.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// A continuación hay dos formas de obtener una tabla de un documento.
// 1 - De la colección "Tables" de un nodo Body:
Table firstTable = doc.FirstSection.Body.Tables[0];

// 2 - Usando el método "GetChild":
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);

// Agrega todas las filas de la tabla actual a la siguiente.
while (secondTable.HasChildNodes)
    firstTable.Rows.Add(secondTable.FirstRow);

// Elimina el contenedor de la tabla vacía.
secondTable.Remove();

doc.Save(ArtifactsDir + "Table.CombineTables.docx");
```

### Ver también

* class [CompositeNode](../)
* espacio de nombres [Aspose.Words](../../compositenode/)
* asamblea [Aspose.Words](../../../)


