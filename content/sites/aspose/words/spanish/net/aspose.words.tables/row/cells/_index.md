---
title: Row.Cells
second_title: Referencia de API de Aspose.Words para .NET
description: Row propiedad. Proporciona acceso escrito a la Célula nodos secundarios de la fila.
type: docs
weight: 20
url: /es/net/aspose.words.tables/row/cells/
---
## Row.Cells property

Proporciona acceso escrito a la **Célula** nodos secundarios de la fila.

```csharp
public CellCollection Cells { get; }
```

### Ejemplos

Muestra cómo recorrer todas las tablas del documento e imprimir el contenido de cada celda.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(2, tables.ToArray().Length);

for (int i = 0; i < tables.Count; i++)
{
    Console.WriteLine($"Start of Table {i}");

    RowCollection rows = tables[i].Rows;

    // Podemos usar el método "ToArray" en una colección de filas para clonarla en una matriz.
    Assert.AreEqual(rows, rows.ToArray());
    Assert.AreNotSame(rows, rows.ToArray());

    for (int j = 0; j < rows.Count; j++)
    {
        Console.WriteLine($"\tStart of Row {j}");

        CellCollection cells = rows[j].Cells;

        // Podemos usar el método "ToArray" en una colección de celdas para clonarla en una matriz.
        Assert.AreEqual(cells, cells.ToArray());
        Assert.AreNotSame(cells, cells.ToArray());

        for (int k = 0; k < cells.Count; k++)
        {
            string cellText = cells[k].ToString(SaveFormat.Text).Trim();
            Console.WriteLine($"\t\tContents of Cell:{k} = \"{cellText}\"");
        }

        Console.WriteLine($"\tEnd of Row {j}");
    }

    Console.WriteLine($"End of Table {i}\n");
}
```

### Ver también

* class [CellCollection](../../cellcollection/)
* class [Row](../)
* espacio de nombres [Aspose.Words.Tables](../../row/)
* asamblea [Aspose.Words](../../../)


