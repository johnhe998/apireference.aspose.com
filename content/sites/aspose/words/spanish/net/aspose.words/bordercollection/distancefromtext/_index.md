---
title: BorderCollection.DistanceFromText
second_title: Referencia de API de Aspose.Words para .NET
description: BorderCollection propiedad. Obtiene o establece la distancia del borde al texto en puntos.
type: docs
weight: 40
url: /es/net/aspose.words/bordercollection/distancefromtext/
---
## BorderCollection.DistanceFromText property

Obtiene o establece la distancia del borde al texto en puntos.

```csharp
public double DistanceFromText { get; set; }
```

### Observaciones

Obtiene la distancia desde el texto para el primer borde.

Establece la distancia desde el texto para todos los bordes de la colección, excepto los bordes diagonales.

No tiene efecto y se restablecerá automáticamente a cero para los bordes de las celdas de la tabla.

### Ejemplos

Muestra cómo crear un borde de página verde ondulado con una sombra.

```csharp
Document doc = new Document();
PageSetup pageSetup = doc.Sections[0].PageSetup;

pageSetup.Borders.LineStyle = LineStyle.DoubleWave;
pageSetup.Borders.LineWidth = 2;
pageSetup.Borders.Color = Color.Green;
pageSetup.Borders.DistanceFromText = 24;
pageSetup.Borders.Shadow = true;

doc.Save(ArtifactsDir + "PageSetup.PageBorders.docx");
```

### Ver también

* class [BorderCollection](../)
* espacio de nombres [Aspose.Words](../../bordercollection/)
* asamblea [Aspose.Words](../../../)


