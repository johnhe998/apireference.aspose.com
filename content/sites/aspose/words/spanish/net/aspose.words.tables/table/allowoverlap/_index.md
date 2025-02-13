---
title: Table.AllowOverlap
second_title: Referencia de API de Aspose.Words para .NET
description: Table propiedad. Obtiene si una tabla flotante permitirá que otros objetos flotantes en el documento superpongan sus extensiones cuando se muestre. El valor predeterminado esverdadero .
type: docs
weight: 70
url: /es/net/aspose.words.tables/table/allowoverlap/
---
## Table.AllowOverlap property

Obtiene si una tabla flotante permitirá que otros objetos flotantes en el documento superpongan sus extensiones cuando se muestre. El valor predeterminado es`verdadero` .

```csharp
public bool AllowOverlap { get; }
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

* class [Table](../)
* espacio de nombres [Aspose.Words.Tables](../../table/)
* asamblea [Aspose.Words](../../../)


