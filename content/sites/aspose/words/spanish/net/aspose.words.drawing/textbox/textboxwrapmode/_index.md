---
title: TextBox.TextBoxWrapMode
second_title: Referencia de API de Aspose.Words para .NET
description: TextBox propiedad. Determina cómo se ajusta el texto dentro de una forma.
type: docs
weight: 100
url: /es/net/aspose.words.drawing/textbox/textboxwrapmode/
---
## TextBox.TextBoxWrapMode property

Determina cómo se ajusta el texto dentro de una forma.

```csharp
public TextBoxWrapMode TextBoxWrapMode { get; set; }
```

### Observaciones

El valor predeterminado esSquare.

### Ejemplos

Muestra cómo configurar un modo de ajuste para el contenido de un cuadro de texto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 300, 300);
TextBox textBox = textBoxShape.TextBox;

// Establecer la propiedad "TextBoxWrapMode" en "TextBoxWrapMode.None" para aumentar el ancho del cuadro de texto
// para acomodar el texto, en caso de que sea lo suficientemente grande.
// Establecer la propiedad "TextBoxWrapMode" en "TextBoxWrapMode.Square" para
// envuelve todo el texto dentro del cuadro de texto, conservando sus dimensiones.
textBox.TextBoxWrapMode = textBoxWrapMode;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Font.Size = 32;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "Shape.TextBoxContentsWrapMode.docx");
```

### Ver también

* enum [TextBoxWrapMode](../../textboxwrapmode/)
* class [TextBox](../)
* espacio de nombres [Aspose.Words.Drawing](../../textbox/)
* asamblea [Aspose.Words](../../../)


