---
title: BorderCollection.Shadow
second_title: Referencia de API de Aspose.Words para .NET
description: BorderCollection propiedad. Obtiene o establece un valor que indica si el borde tiene sombra.
type: docs
weight: 110
url: /es/net/aspose.words/bordercollection/shadow/
---
## BorderCollection.Shadow property

Obtiene o establece un valor que indica si el borde tiene sombra.

```csharp
public bool Shadow { get; set; }
```

### Observaciones

Obtiene el valor del primer borde de la colección.

Establece el valor de todos los bordes de la colección, excepto los bordes diagonales.

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


