---
title: ShapeBase.DistanceBottom
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Devuelve o establece la distancia en puntos entre el texto del documento y el borde inferior de la forma.
type: docs
weight: 130
url: /es/net/aspose.words.drawing/shapebase/distancebottom/
---
## ShapeBase.DistanceBottom property

Devuelve o establece la distancia (en puntos) entre el texto del documento y el borde inferior de la forma.

```csharp
public double DistanceBottom { get; set; }
```

### Observaciones

El valor predeterminado es 0.

Solo tiene efecto para las formas de nivel superior.

### Ejemplos

Muestra cómo establecer la distancia de ajuste para un texto que rodea una forma.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta un rectángulo y haz que el texto se ajuste bien alrededor de sus límites.
Shape shape = builder.InsertShape(ShapeType.Rectangle, 150, 150);
shape.WrapType = WrapType.Tight;

// Establezca la distancia mínima entre la forma y el texto circundante en 40 puntos desde todos los lados.
shape.DistanceTop = 40;
shape.DistanceBottom = 40;
shape.DistanceLeft = 40;
shape.DistanceRight = 40;

// Mueva la forma más cerca del centro de la página y luego gire la forma 60 grados en el sentido de las agujas del reloj.
shape.Top = 75;
shape.Left = 150; 
shape.Rotation = 60;

// Agrega texto que envolverá la forma.
builder.Font.Size = 24;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
              "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

doc.Save(ArtifactsDir + "Shape.Coordinates.docx");
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


