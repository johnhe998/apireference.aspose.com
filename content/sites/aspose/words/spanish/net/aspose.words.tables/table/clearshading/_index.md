---
title: Table.ClearShading
second_title: Referencia de API de Aspose.Words para .NET
description: Table método. Elimina todo el sombreado de la mesa.
type: docs
weight: 380
url: /es/net/aspose.words.tables/table/clearshading/
---
## Table.ClearShading method

Elimina todo el sombreado de la mesa.

```csharp
public void ClearShading()
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

### Ver también

* class [Table](../)
* espacio de nombres [Aspose.Words.Tables](../../table/)
* asamblea [Aspose.Words](../../../)


