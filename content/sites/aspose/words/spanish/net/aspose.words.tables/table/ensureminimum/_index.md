---
title: Table.EnsureMinimum
second_title: Referencia de API de Aspose.Words para .NET
description: Table método. Si la tabla no tiene filas crea y agrega una Fila .
type: docs
weight: 400
url: /es/net/aspose.words.tables/table/ensureminimum/
---
## Table.EnsureMinimum method

Si la tabla no tiene filas, crea y agrega una **Fila** .

```csharp
public void EnsureMinimum()
```

### Ejemplos

Muestra cómo garantizar que un nodo de tabla contenga los nodos que necesitamos para agregar contenido.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);

// Las tablas contienen filas, que contienen celdas, que pueden contener párrafos
// con elementos típicos como carreras, formas e incluso otras tablas.
// Nuestra nueva tabla no tiene ninguno de estos nodos, y no podemos agregarle contenido hasta que lo tenga.
Assert.AreEqual(0, table.GetChildNodes(NodeType.Any, true).Count);

// Llamar al método "EnsureMinimum" en una tabla asegurará que
// la tabla tiene al menos una fila y una celda con un párrafo vacío.
table.EnsureMinimum();
table.FirstRow.FirstCell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### Ver también

* class [Table](../)
* espacio de nombres [Aspose.Words.Tables](../../table/)
* asamblea [Aspose.Words](../../../)


