---
title: GridCells.Item
second_title: Aspose.Cells for .NET API Reference
description: GridCells property. Gets Cell item within the worksheet
type: docs
url: /net/aspose.cells.griddesktop.data/gridcells/item/
---
## GridCells indexer (1 of 3)

Gets Cell item within the worksheet

```csharp
public GridCell this[int index] { get; }
```

| Parameter | Description |
| --- | --- |
| index | The zero based index of the element. |

### Property Value

The element at the specified index.

### Remarks

This is the indexer for the Cells class. Gets the cell element at the specified index.

### See Also

* class [GridCell](../../gridcell/)
* class [GridCells](../)
* namespace [Aspose.Cells.GridDesktop.Data](../../../aspose.cells.griddesktop.data/)
* assembly [Aspose.Cells.GridDesktop](../../../)

---

## GridCells indexer (2 of 3)

Gets the Cell element at the specified cell row index and column index.

```csharp
public GridCell this[int row, int column] { get; }
```

| Parameter | Description |
| --- | --- |
| row | Row index. |
| column | Column index. |

### Return Value

The Cell object.

### Examples

```csharp
[C#]

Cells cells = excel.Worksheets[0].Cells;
Cell cell = cells[0, 0];	//Gets the cell at "A1"

[Visual Basic]

Dim cells As Cells =  excel.WorkSheets(0).Cells
Dim cell As Cell =  cells(0,0)  'Gets the cell at "A1"
```

### See Also

* class [GridCell](../../gridcell/)
* class [GridCells](../)
* namespace [Aspose.Cells.GridDesktop.Data](../../../aspose.cells.griddesktop.data/)
* assembly [Aspose.Cells.GridDesktop](../../../)

---

## GridCells indexer (3 of 3)

Gets the Cell element at the specified cell name.

```csharp
public GridCell this[string cellName] { get; }
```

| Parameter | Description |
| --- | --- |
| cellName | Cell name,including its column letter and row number, for example A5. |

### Return Value

A Cell object

### Examples

```csharp
[C#]

Cells cells = excel.Worksheets[0].Cells;
Cell cell = cells["A1"];	//Gets the cell at "A1"

[Visual Basic]

Dim cells As Cells =  excel.Worksheets(0).Cells
Dim cell As Cell =  cells("A1")  'Gets the cell at "A1"
```

### See Also

* class [GridCell](../../gridcell/)
* class [GridCells](../)
* namespace [Aspose.Cells.GridDesktop.Data](../../../aspose.cells.griddesktop.data/)
* assembly [Aspose.Cells.GridDesktop](../../../)


