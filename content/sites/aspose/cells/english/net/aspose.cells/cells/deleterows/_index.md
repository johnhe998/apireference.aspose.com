---
title: Cells.DeleteRows
second_title: Aspose.Cells for .NET API Reference
description: Cells method. Deletes several rows
type: docs
url: /net/aspose.cells/cells/deleterows/
---
## DeleteRows(int, int) {#deleterows}

Deletes several rows.

```csharp
public bool DeleteRows(int rowIndex, int totalRows)
```

| Parameter | Type | Description |
| --- | --- | --- |
| rowIndex | Int32 | The first row index to be deleted. |
| totalRows | Int32 | Number of rows to be deleted. |

### Remarks

If the deleted range contains the top part(not whole) of the table(ListObject), the ranged could not be deleted and nothing will be done.It works as MS Excel.

### See Also

* class [Cells](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)

---

## DeleteRows(int, int, bool) {#deleterows_1}

Deletes multiple rows in the worksheet.

```csharp
public bool DeleteRows(int rowIndex, int totalRows, bool updateReference)
```

| Parameter | Type | Description |
| --- | --- | --- |
| rowIndex | Int32 | Row index. |
| totalRows | Int32 | Number of rows to be deleted. |
| updateReference | Boolean | Indicates if update references in other worksheets. |

### See Also

* class [Cells](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)


