---
title: Table.VerticalAnchor
second_title: Referencia de API de Aspose.Words para .NET
description: Table propiedad. Obtiene el objeto base a partir del cual se debe calcular el posicionamiento vertical de la tabla flotante. El valor predeterminado esMargin .
type: docs
weight: 340
url: /es/net/aspose.words.tables/table/verticalanchor/
---
## Table.VerticalAnchor property

Obtiene el objeto base a partir del cual se debe calcular el posicionamiento vertical de la tabla flotante. El valor predeterminado esMargin .

```csharp
public RelativeVerticalPosition VerticalAnchor { get; set; }
```

### Ejemplos

Muestra cómo trabajar con propiedades de tablas flotantes.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

if (table.TextWrapping == TextWrapping.Around)
{
    Assert.AreEqual(RelativeHorizontalPosition.Margin, table.HorizontalAnchor);
    Assert.AreEqual(RelativeVerticalPosition.Paragraph, table.VerticalAnchor);
    Assert.AreEqual(false, table.AllowOverlap);

    // Solo Margen, Página, Columna disponibles en RelativeHorizontalPosition para el setter HorizontalAnchor.
    // Se lanzará ArgumentException para cualquier otro valor.
    table.HorizontalAnchor = RelativeHorizontalPosition.Column;

    // Solo Margen, Página, Párrafo disponible en RelativeVerticalPosition para el setter VerticalAnchor.
    // Se lanzará ArgumentException para cualquier otro valor.
    table.VerticalAnchor = RelativeVerticalPosition.Page;
}
```

### Ver también

* enum [RelativeVerticalPosition](../../../aspose.words.drawing/relativeverticalposition/)
* class [Table](../)
* espacio de nombres [Aspose.Words.Tables](../../table/)
* asamblea [Aspose.Words](../../../)


