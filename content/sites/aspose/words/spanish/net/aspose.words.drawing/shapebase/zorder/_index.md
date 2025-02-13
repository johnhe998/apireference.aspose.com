---
title: ShapeBase.ZOrder
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Determina el orden de visualización de las formas superpuestas.
type: docs
weight: 550
url: /es/net/aspose.words.drawing/shapebase/zorder/
---
## ShapeBase.ZOrder property

Determina el orden de visualización de las formas superpuestas.

```csharp
public int ZOrder { get; set; }
```

### Observaciones

Solo tiene efecto para las formas de nivel superior.

El valor predeterminado es 0.

El número representa la precedencia de apilamiento. Una forma con un número más alto se mostrará como si estuviera superpuesta (en "frente") a una forma con un número más bajo.

El orden de las formas superpuestas es independiente para las formas en el encabezado y en el texto main del documento.

El orden de visualización de las formas secundarias en una forma de grupo está determinado por su order dentro de la forma de grupo.

### Ejemplos

Muestra cómo manipular el orden de las formas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta tres rectángulos de diferentes colores que se superponen parcialmente entre sí.
// Cuando insertamos una forma que se superpone a otra forma, Aspose.Words coloca la forma más nueva encima de la anterior.
// El rectángulo verde claro se superpondrá al rectángulo azul claro y lo oscurecerá parcialmente,
// y el rectángulo azul claro oscurecerá el rectángulo naranja.
Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);
shape.FillColor = Color.Orange;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 150,
    RelativeVerticalPosition.TopMargin, 150, 200, 200, WrapType.None);
shape.FillColor = Color.LightBlue;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 200,
    RelativeVerticalPosition.TopMargin, 200, 200, 200, WrapType.None);
shape.FillColor = Color.LightGreen;

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

// La propiedad "ZOrder" de una forma determina su prioridad de apilamiento entre otras formas superpuestas.
// Si dos formas superpuestas tienen diferentes valores de "ZOrder",
  // Microsoft Word colocará la forma con un valor más alto sobre la forma con el valor más bajo.
// Establecer los valores de "ZOrder" de nuestras formas para colocar el primer rectángulo naranja sobre el segundo azul claro
// y el segundo rectángulo azul claro sobre el tercer rectángulo verde claro.
// Esto invertirá su orden de apilamiento original.
shapes[0].ZOrder = 3;
shapes[1].ZOrder = 2;
shapes[2].ZOrder = 1;

doc.Save(ArtifactsDir + "Shape.ZOrder.docx");
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


