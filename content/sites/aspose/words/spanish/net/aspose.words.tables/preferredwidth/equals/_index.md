---
title: PreferredWidth.Equals
second_title: Referencia de API de Aspose.Words para .NET
description: PreferredWidth método. Determina si el PreferredWidth especificado tiene el mismo valor que el PreferredWidth actual.
type: docs
weight: 60
url: /es/net/aspose.words.tables/preferredwidth/equals/
---
## Equals(PreferredWidth) {#equals}

Determina si el PreferredWidth especificado tiene el mismo valor que el PreferredWidth actual.

```csharp
public bool Equals(PreferredWidth other)
```

### Ejemplos

Muestra cómo establecer un ancho preferido para las celdas de la tabla.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Hay dos formas de aplicar la clase "PreferredWidth" a las celdas de la tabla.
// 1 - Establecer un ancho preferido absoluto basado en puntos:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - Establecer un ancho preferido relativo basado en el porcentaje del ancho de la tabla:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// Una celda sin un ancho preferido especificado ocupará el resto del espacio disponible.
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// Cada configuración de la propiedad "PreferredWidth" crea un nuevo objeto.
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### Ver también

* class [PreferredWidth](../)
* espacio de nombres [Aspose.Words.Tables](../../preferredwidth/)
* asamblea [Aspose.Words](../../../)

---

## Equals(object) {#equals_1}

Determina si el objeto especificado tiene el mismo valor que el objeto actual.

```csharp
public override bool Equals(object obj)
```

### Ejemplos

Muestra cómo establecer un ancho preferido para las celdas de la tabla.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Hay dos formas de aplicar la clase "PreferredWidth" a las celdas de la tabla.
// 1 - Establecer un ancho preferido absoluto basado en puntos:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - Establecer un ancho preferido relativo basado en el porcentaje del ancho de la tabla:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// Una celda sin un ancho preferido especificado ocupará el resto del espacio disponible.
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// Cada configuración de la propiedad "PreferredWidth" crea un nuevo objeto.
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### Ver también

* class [PreferredWidth](../)
* espacio de nombres [Aspose.Words.Tables](../../preferredwidth/)
* asamblea [Aspose.Words](../../../)


