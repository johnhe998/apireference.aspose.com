---
title: Shape.LastParagraph
second_title: Referencia de API de Aspose.Words para .NET
description: Shape propiedad. Obtiene el último párrafo de la forma.
type: docs
weight: 120
url: /es/net/aspose.words.drawing/shape/lastparagraph/
---
## Shape.LastParagraph property

Obtiene el último párrafo de la forma.

```csharp
public Paragraph LastParagraph { get; }
```

### Ejemplos

Muestra cómo establecer la orientación del texto dentro de un cuadro de texto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Mueva el generador de documentos dentro del cuadro de texto y agregue texto.
builder.MoveTo(textBoxShape.LastParagraph);
builder.Writeln("Hello world!");
builder.Write("Hello again!");

// Establecer la propiedad "LayoutFlow" para establecer una orientación para el contenido de texto de este cuadro de texto.
textBox.LayoutFlow = layoutFlow;

doc.Save(ArtifactsDir + "Shape.TextBoxLayoutFlow.docx");
```

### Ver también

* class [Paragraph](../../../aspose.words/paragraph/)
* class [Shape](../)
* espacio de nombres [Aspose.Words.Drawing](../../shape/)
* asamblea [Aspose.Words](../../../)


