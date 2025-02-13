---
title: TextColumn.SpaceAfter
second_title: Referencia de API de Aspose.Words para .NET
description: TextColumn propiedad. Obtiene o establece el espacio entre esta columna y la siguiente columna en puntos. No se requiere para la última columna.
type: docs
weight: 10
url: /es/net/aspose.words/textcolumn/spaceafter/
---
## TextColumn.SpaceAfter property

Obtiene o establece el espacio entre esta columna y la siguiente columna en puntos. No se requiere para la última columna.

```csharp
public double SpaceAfter { get; set; }
```

### Ejemplos

Muestra cómo crear columnas espaciadas irregularmente.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
PageSetup pageSetup = builder.PageSetup;

TextColumnCollection columns = pageSetup.TextColumns;
columns.EvenlySpaced = false;
columns.SetCount(2);

// Determinar la cantidad de espacio que tenemos disponible para organizar columnas.
double contentWidth = pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin;

Assert.AreEqual(470.30d, contentWidth, 0.01d);

// Establecer la primera columna para que sea estrecha.
TextColumn column = columns[0];
column.Width = 100;
column.SpaceAfter = 20;

// Establecer la segunda columna para ocupar el resto del espacio disponible dentro de los márgenes de la página.
column = columns[1];
column.Width = contentWidth - column.Width - column.SpaceAfter;

builder.Writeln("Narrow column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Wide column 2.");

doc.Save(ArtifactsDir + "PageSetup.CustomColumnWidth.docx");
```

### Ver también

* class [TextColumn](../)
* espacio de nombres [Aspose.Words](../../textcolumn/)
* asamblea [Aspose.Words](../../../)


