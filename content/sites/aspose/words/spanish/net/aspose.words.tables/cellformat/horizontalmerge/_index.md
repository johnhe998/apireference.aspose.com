---
title: CellFormat.HorizontalMerge
second_title: Referencia de API de Aspose.Words para .NET
description: CellFormat propiedad. Especifica cómo se fusiona la celda horizontalmente con otras celdas de la fila.
type: docs
weight: 40
url: /es/net/aspose.words.tables/cellformat/horizontalmerge/
---
## CellFormat.HorizontalMerge property

Especifica cómo se fusiona la celda horizontalmente con otras celdas de la fila.

```csharp
public CellMerge HorizontalMerge { get; set; }
```

### Ejemplos

Muestra cómo fusionar celdas de tabla horizontalmente.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta una celda en la primera columna de la primera fila.
// Esta celda será la primera en un rango de celdas combinadas horizontalmente.
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Inserta una celda en la segunda columna de la primera fila. En lugar de agregar contenido de texto,
// fusionaremos esta celda con la primera celda que agregamos directamente a la izquierda.
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();

// Inserta dos celdas más no fusionadas en la segunda fila.
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.InsertCell();
builder.Write("Text in unmerged cell.");
builder.InsertCell();
builder.Write("Text in unmerged cell.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "CellFormat.HorizontalMerge.docx");
```

Imprime el tipo de combinación horizontal y vertical de una celda.

```csharp
public void CheckCellsMerged()
{
    Document doc = new Document(MyDir + "Table with merged cells.docx");
    Table table = doc.FirstSection.Body.Tables[0];

    foreach (Row row in table.Rows.OfType<Row>())
        foreach (Cell cell in row.Cells.OfType<Cell>())
            Console.WriteLine(PrintCellMergeType(cell));
}

public string PrintCellMergeType(Cell cell)
{
    bool isHorizontallyMerged = cell.CellFormat.HorizontalMerge != CellMerge.None;
    bool isVerticallyMerged = cell.CellFormat.VerticalMerge != CellMerge.None;
    string cellLocation =
        $"R{cell.ParentRow.ParentTable.IndexOf(cell.ParentRow) + 1}, C{cell.ParentRow.IndexOf(cell) + 1}";

    if (isHorizontallyMerged && isVerticallyMerged)
        return $"The cell at {cellLocation} is both horizontally and vertically merged";
    if (isHorizontallyMerged)
        return $"The cell at {cellLocation} is horizontally merged.";

    return isVerticallyMerged ? $"The cell at {cellLocation} is vertically merged" : $"The cell at {cellLocation} is not merged";
}
```

### Ver también

* property [VerticalMerge](../verticalmerge/)
* enum [CellMerge](../../cellmerge/)
* class [CellFormat](../)
* espacio de nombres [Aspose.Words.Tables](../../cellformat/)
* asamblea [Aspose.Words](../../../)


