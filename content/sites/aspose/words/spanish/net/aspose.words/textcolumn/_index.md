---
title: Class TextColumn
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.TextColumn clase. Representa una sola columna de texto. Columna de texto es miembro de laTextColumnCollection colección. La Columnas de texto colección incluye todas las columnas en una sección de un documento.
type: docs
weight: 6090
url: /es/net/aspose.words/textcolumn/
---
## TextColumn class

Representa una sola columna de texto. **Columna de texto** es miembro de la[`TextColumnCollection`](../textcolumncollection/) colección. La **Columnas de texto** colección incluye todas las columnas en una sección de un documento.

```csharp
public class TextColumn
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [SpaceAfter](../../aspose.words/textcolumn/spaceafter/) { get; set; } | Obtiene o establece el espacio entre esta columna y la siguiente columna en puntos. No se requiere para la última columna. |
| [Width](../../aspose.words/textcolumn/width/) { get; set; } | Obtiene o establece el ancho de la columna de texto en puntos. |

### Observaciones

**Columna de texto** los objetos solo se utilizan para especificar columnas con ancho y espaciado personalizados. Si desea que las columnas del documento tengan el mismo ancho, configure TextColumns.[`EvenlySpaced`](../textcolumncollection/evenlyspaced/) a **verdadero**.

cuando un nuevo **Columna de texto** se crea, tiene el ancho y el espaciado establecidos en cero.

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

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


