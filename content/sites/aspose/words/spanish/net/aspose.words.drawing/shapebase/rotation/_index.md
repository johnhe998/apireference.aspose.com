---
title: ShapeBase.Rotation
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Define el ángulo en grados con el que se rota una forma. El valor positivo corresponde al ángulo de rotación en el sentido de las agujas del reloj.
type: docs
weight: 430
url: /es/net/aspose.words.drawing/shapebase/rotation/
---
## ShapeBase.Rotation property

Define el ángulo (en grados) con el que se rota una forma. El valor positivo corresponde al ángulo de rotación en el sentido de las agujas del reloj.

```csharp
public double Rotation { get; set; }
```

### Observaciones

El valor predeterminado es 0.

### Ejemplos

Muestra cómo insertar y rotar una imagen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta una forma con una imagen.
Shape shape = builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
Assert.True(shape.CanHaveImage);
Assert.True(shape.HasImage);

// Gira la imagen 45 grados en el sentido de las agujas del reloj.
shape.Rotation = 45;

doc.Save(ArtifactsDir + "Shape.Rotate.docx");
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


