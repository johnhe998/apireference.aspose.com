---
title: Stroke.Color2
second_title: Referencia de API de Aspose.Words para .NET
description: Stroke propiedad. Define un segundo color para un trazo.
type: docs
weight: 30
url: /es/net/aspose.words.drawing/stroke/color2/
---
## Stroke.Color2 property

Define un segundo color para un trazo.

```csharp
public Color Color2 { get; set; }
```

### Observaciones

El valor predeterminado para un[`Shape`](../../shape/) es White.

### Ejemplos

Muestra cómo procesar funciones de trazo de forma.

```csharp
Document doc = new Document(MyDir + "Shape stroke pattern border.docx");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
Stroke stroke = shape.Stroke;

// Los trazos pueden tener dos colores, que se utilizan para crear un patrón definido por datos de imagen de dos tonos.
// Los trazos con un solo color no usan la propiedad Color2.
Assert.AreEqual(Color.FromArgb(255, 128, 0, 0), stroke.Color);
Assert.AreEqual(Color.FromArgb(255, 255, 255, 0), stroke.Color2);

Assert.NotNull(stroke.ImageBytes);
File.WriteAllBytes(ArtifactsDir + "Drawing.StrokePattern.png", stroke.ImageBytes);
```

### Ver también

* class [Stroke](../)
* espacio de nombres [Aspose.Words.Drawing](../../stroke/)
* asamblea [Aspose.Words](../../../)


