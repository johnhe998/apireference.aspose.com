---
title: ShapeBase.LocalToParent
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase método. Convierte un valor del espacio de coordenadas local en el espacio de coordenadas de la forma principal.
type: docs
weight: 610
url: /es/net/aspose.words.drawing/shapebase/localtoparent/
---
## ShapeBase.LocalToParent method

Convierte un valor del espacio de coordenadas local en el espacio de coordenadas de la forma principal.

```csharp
public PointF LocalToParent(PointF value)
```

### Ejemplos

Muestra cómo trasladar la ubicación de las coordenadas x e y en el plano de coordenadas de una forma a una ubicación en el plano de coordenadas de la forma principal.

```csharp
Document doc = new Document();

// Inserte una forma de grupo y colóquela 100 puntos debajo y a la derecha de
// el punto de origen de las coordenadas x e y del documento.
GroupShape group = new GroupShape(doc);
group.Bounds = new RectangleF(100, 100, 500, 500);

// Use el método "LocalToParent" para determinar que (0, 0) en las coordenadas x e y internas del grupo
// se encuentra en (100, 100) del sistema de coordenadas de su forma principal. El elemento principal de la forma de grupo es el propio documento.
Assert.AreEqual(new PointF(100, 100), group.LocalToParent(new PointF(0, 0)));

// De forma predeterminada, el plano de coordenadas internas de una forma tiene la esquina superior izquierda en (0, 0),
// y la esquina inferior derecha en (1000, 1000). Debido a su tamaño, nuestra forma de grupo cubre un área de 500pt x 500pt
// en el plano del documento. Esto significa que un movimiento de 1 pt en el plano de coordenadas del documento se traducirá
// a un movimiento de 2 puntos en el plano de coordenadas de la forma del grupo.
Assert.AreEqual(new PointF(150, 150), group.LocalToParent(new PointF(100, 100)));
Assert.AreEqual(new PointF(200, 200), group.LocalToParent(new PointF(200, 200)));
Assert.AreEqual(new PointF(250, 250), group.LocalToParent(new PointF(300, 300)));

// Mueva el origen del eje xey de la forma del grupo desde la esquina superior izquierda hacia el centro.
// Esto compensará aún más las coordenadas internas del grupo en relación con las coordenadas del documento.
group.CoordOrigin = new Point(-250, -250);

Assert.AreEqual(new PointF(375, 375), group.LocalToParent(new PointF(300, 300)));

// Cambiar la escala del plano de coordenadas también afectará las ubicaciones relativas.
group.CoordSize = new Size(500, 500);

Assert.AreEqual(new PointF(650, 650), group.LocalToParent(new PointF(300, 300)));

// Si deseamos agregar una forma a este grupo mientras definimos su ubicación en función de una ubicación en el documento,
// primero necesitaremos confirmar una ubicación en la forma del grupo que coincida con la ubicación del documento.
Assert.AreEqual(new PointF(700, 700), group.LocalToParent(new PointF(350, 350)));

Shape shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 700,
    Top = 700
};

group.AppendChild(shape);
doc.FirstSection.Body.FirstParagraph.AppendChild(group);

doc.Save(ArtifactsDir + "Shape.LocalToParent.docx");
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


