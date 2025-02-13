---
title: ShapeBase.BehindText
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Especifica si la forma está debajo o encima del texto.
type: docs
weight: 50
url: /es/net/aspose.words.drawing/shapebase/behindtext/
---
## ShapeBase.BehindText property

Especifica si la forma está debajo o encima del texto.

```csharp
public bool BehindText { get; set; }
```

### Observaciones

Solo tiene efecto para las formas de nivel superior.

El valor predeterminado es **falso**.

### Ejemplos

Muestra cómo insertar una imagen flotante en el centro de una página.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta una imagen flotante que aparecerá detrás del texto superpuesto y alinéala con el centro de la página.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


