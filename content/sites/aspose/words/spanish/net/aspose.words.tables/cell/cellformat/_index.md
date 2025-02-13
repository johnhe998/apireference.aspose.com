---
title: Cell.CellFormat
second_title: Referencia de API de Aspose.Words para .NET
description: Cell propiedad. Proporciona acceso a las propiedades de formato de la celda.
type: docs
weight: 20
url: /es/net/aspose.words.tables/cell/cellformat/
---
## Cell.CellFormat property

Proporciona acceso a las propiedades de formato de la celda.

```csharp
public CellFormat CellFormat { get; }
```

### Ejemplos

Muestra cómo modificar el formato de una celda de tabla.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];
Cell firstCell = table.FirstRow.FirstCell;

// Use la propiedad "CellFormat" de una celda para establecer un formato que modifique la apariencia de esa celda.
firstCell.CellFormat.Width = 30;
firstCell.CellFormat.Orientation = TextOrientation.Downward;
firstCell.CellFormat.Shading.ForegroundPatternColor = Color.LightGreen;

doc.Save(ArtifactsDir + "Table.CellFormat.docx");
```

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

Muestra cómo modificar el formato de filas y celdas en una tabla.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("City");
builder.InsertCell();
builder.Write("Country");
builder.EndRow();
builder.InsertCell();
builder.Write("London");
builder.InsertCell();
builder.Write("U.K.");
builder.EndTable();

// Usa la propiedad "RowFormat" de la primera fila para modificar el formato
// del contenido de todas las celdas de esta fila.
RowFormat rowFormat = table.FirstRow.RowFormat;
rowFormat.Height = 25;
rowFormat.Borders[BorderType.Bottom].Color = Color.Red;

// Use la propiedad "CellFormat" de la primera celda en la última fila para modificar el formato del contenido de esa celda.
CellFormat cellFormat = table.LastRow.FirstCell.CellFormat;
cellFormat.Width = 100;
cellFormat.Shading.BackgroundPatternColor = Color.Orange;

doc.Save(ArtifactsDir + "Table.RowCellFormat.docx");
```

### Ver también

* class [CellFormat](../../cellformat/)
* class [Cell](../)
* espacio de nombres [Aspose.Words.Tables](../../cell/)
* asamblea [Aspose.Words](../../../)


