---
title: TextBox.InternalMarginTop
second_title: Referencia de API de Aspose.Words para .NET
description: TextBox propiedad. Especifica el margen superior interior en puntos para una forma.
type: docs
weight: 50
url: /es/net/aspose.words.drawing/textbox/internalmargintop/
---
## TextBox.InternalMarginTop property

Especifica el margen superior interior en puntos para una forma.

```csharp
public double InternalMarginTop { get; set; }
```

### Observaciones

El valor predeterminado es 1/20 de pulgada.

### Ejemplos

Muestra cómo establecer márgenes internos para un cuadro de texto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta otro cuadro de texto con márgenes específicos.
Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 100, 100);
TextBox textBox = textBoxShape.TextBox;
textBox.InternalMarginTop = 15;
textBox.InternalMarginBottom = 15;
textBox.InternalMarginLeft = 15;
textBox.InternalMarginRight = 15;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text placed according to textbox margins.");

doc.Save(ArtifactsDir + "Shape.TextBoxMargins.docx");
```

### Ver también

* class [TextBox](../)
* espacio de nombres [Aspose.Words.Drawing](../../textbox/)
* asamblea [Aspose.Words](../../../)


