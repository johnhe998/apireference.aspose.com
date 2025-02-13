---
title: Table.ClearBorders
second_title: Referencia de API de Aspose.Words para .NET
description: Table método. Elimina todos los bordes de tablas y celdas de esta tabla.
type: docs
weight: 370
url: /es/net/aspose.words.tables/table/clearborders/
---
## Table.ClearBorders method

Elimina todos los bordes de tablas y celdas de esta tabla.

```csharp
public void ClearBorders()
```

### Ejemplos

Muestra cómo aplicar un borde de contorno a una tabla.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Alinea la tabla al centro de la página.
table.Alignment = TableAlignment.Center;

// Limpia cualquier borde existente y sombreado de la tabla.
table.ClearBorders();
table.ClearShading();

// Agrega bordes verdes al contorno de la tabla.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// Rellena las celdas con un color sólido verde claro.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

Muestra cómo eliminar todos los bordes de una tabla.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

// Modificar el color y grosor del borde superior.
Border topBorder = table.FirstRow.RowFormat.Borders[BorderType.Top];
table.SetBorder(BorderType.Top, LineStyle.Double, 1.5, Color.Red, true);

Assert.AreEqual(1.5d, topBorder.LineWidth);
Assert.AreEqual(Color.Red.ToArgb(), topBorder.Color.ToArgb());
Assert.AreEqual(LineStyle.Double, topBorder.LineStyle);

// Limpia los bordes de todas las celdas de la tabla y luego guarda el documento.
table.ClearBorders();
doc.Save(ArtifactsDir + "Table.ClearBorders.docx");

// Verifica los valores de las propiedades de la tabla después de volver a abrir el documento.
doc = new Document(ArtifactsDir + "Table.ClearBorders.docx");
table = doc.FirstSection.Body.Tables[0];
topBorder = table.FirstRow.RowFormat.Borders[BorderType.Top];

Assert.AreEqual(0.0d, topBorder.LineWidth);
Assert.AreEqual(Color.Empty.ToArgb(), topBorder.Color.ToArgb());
Assert.AreEqual(LineStyle.None, topBorder.LineStyle);
```

### Ver también

* class [Table](../)
* espacio de nombres [Aspose.Words.Tables](../../table/)
* asamblea [Aspose.Words](../../../)


