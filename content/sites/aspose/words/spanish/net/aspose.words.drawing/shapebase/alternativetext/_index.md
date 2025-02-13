---
title: ShapeBase.AlternativeText
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Define el texto alternativo que se mostrará en lugar de un gráfico.
type: docs
weight: 20
url: /es/net/aspose.words.drawing/shapebase/alternativetext/
---
## ShapeBase.AlternativeText property

Define el texto alternativo que se mostrará en lugar de un gráfico.

```csharp
public string AlternativeText { get; set; }
```

### Observaciones

El valor predeterminado es una cadena vacía.

### Ejemplos

Muestra cómo usar el texto alternativo de una forma.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertShape(ShapeType.Cube, 150, 150);
shape.Name = "MyCube";

shape.AlternativeText = "Alt text for MyCube.";

// Podemos acceder al texto alternativo de una forma haciendo clic con el botón derecho y luego a través de "Formatear autoforma" -> "Texto alternativo".
doc.Save(ArtifactsDir + "Shape.AltText.docx");

// Guarde el documento en HTML y luego elimine la imagen vinculada que pertenece a nuestra forma.
// El navegador que está leyendo nuestro HTML mostrará el texto alternativo en lugar de la imagen que falta.
doc.Save(ArtifactsDir + "Shape.AltText.html");
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


