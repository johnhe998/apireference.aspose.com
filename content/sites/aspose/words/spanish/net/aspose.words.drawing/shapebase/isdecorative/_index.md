---
title: ShapeBase.IsDecorative
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Obtiene o establece el indicador que especifica si la forma es decorativa en el documento.
type: docs
weight: 230
url: /es/net/aspose.words.drawing/shapebase/isdecorative/
---
## ShapeBase.IsDecorative property

Obtiene o establece el indicador que especifica si la forma es decorativa en el documento.

```csharp
public bool IsDecorative { get; set; }
```

### Observaciones

Tenga en cuenta que la forma no tiene vacío[`AlternativeText`](../alternativetext/) no puede ser decorativo.

### Ejemplos

Muestra cómo establecer que la forma sea decorativa.

```csharp
Document doc = new Document(MyDir + "Decorative shapes.docx");

Shape shape = (Shape) doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(shape.IsDecorative);

// Si "AlternativeText" no está vacío, la forma no puede ser decorativa.
// Es por eso que nuestro valor ha cambiado a 'falso'.
shape.AlternativeText = "Alternative text.";
Assert.False(shape.IsDecorative);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
// Crea una nueva forma como decorativa.
shape = builder.InsertShape(ShapeType.Rectangle, 100, 100);
shape.IsDecorative = true;

doc.Save(ArtifactsDir + "Shape.IsDecorative.docx");
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


