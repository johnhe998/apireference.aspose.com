---
title: Table.ConvertToHorizontallyMergedCells
second_title: Referencia de API de Aspose.Words para .NET
description: Table método. Convierte celdas fusionadas horizontalmente por ancho en celdas fusionadas porHorizontalMerge .
type: docs
weight: 390
url: /es/net/aspose.words.tables/table/converttohorizontallymergedcells/
---
## Table.ConvertToHorizontallyMergedCells method

Convierte celdas fusionadas horizontalmente por ancho en celdas fusionadas por[`HorizontalMerge`](../../cellformat/horizontalmerge/) .

```csharp
public void ConvertToHorizontallyMergedCells()
```

### Observaciones

Las celdas de la tabla se pueden fusionar horizontalmente usando banderas de fusión[`HorizontalMerge`](../../cellformat/horizontalmerge/) o usando el ancho de celda[`Width`](../../cellformat/width/).

Cuando la celda de la tabla se fusiona por la propiedad de ancho[`HorizontalMerge`](../../cellformat/horizontalmerge/) no tiene sentido, pero a veces tener banderas de combinación es una forma más conveniente.

Utilice este método para transformar las celdas de la tabla fusionadas horizontalmente por ancho en celdas fusionadas por banderas de fusión.

### Ejemplos

Muestra cómo convertir celdas combinadas horizontalmente por ancho en celdas combinadas por CellFormat.HorizontalMerge.

```csharp
Document doc = new Document(MyDir + "Table with merged cells.docx");

// Microsoft Word ya no escribe banderas de combinación, sino que define las celdas combinadas por ancho.
// Aspose.Words por defecto define solo 5 celdas en una fila, y ninguna de ellas tiene el indicador de combinación horizontal,
// aunque había 7 celdas en la fila antes de que tuviera lugar la fusión horizontal.
Table table = doc.FirstSection.Body.Tables[0];
Row row = table.Rows[0];

Assert.AreEqual(5, row.Cells.Count);
Assert.True(row.Cells.All(c => ((Cell)c).CellFormat.HorizontalMerge == CellMerge.None));

// Use el método "ConvertToHorizontallyMergedCells" para convertir celdas combinadas horizontalmente
// por su ancho a la celda fusionada horizontalmente por banderas.
// Ahora, tenemos 7 celdas, y algunas de ellas tienen valores de fusión horizontales.
table.ConvertToHorizontallyMergedCells();
row = table.Rows[0];

Assert.AreEqual(7, row.Cells.Count);

Assert.AreEqual(CellMerge.None, row.Cells[0].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.First, row.Cells[1].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.Previous, row.Cells[2].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.None, row.Cells[3].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.First, row.Cells[4].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.Previous, row.Cells[5].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.None, row.Cells[6].CellFormat.HorizontalMerge);
```

### Ver también

* class [Table](../)
* espacio de nombres [Aspose.Words.Tables](../../table/)
* asamblea [Aspose.Words](../../../)


