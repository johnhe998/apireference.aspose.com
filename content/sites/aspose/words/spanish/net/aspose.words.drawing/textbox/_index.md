---
title: Class TextBox
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.TextBox clase. Define atributos que especifican cómo se muestra un texto dentro de una forma.
type: docs
weight: 1170
url: /es/net/aspose.words.drawing/textbox/
---
## TextBox class

Define atributos que especifican cómo se muestra un texto dentro de una forma.

```csharp
public class TextBox
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [FitShapeToText](../../aspose.words.drawing/textbox/fitshapetotext/) { get; set; } | Determina si Microsoft Word aumentará la forma para que se ajuste al texto. |
| [InternalMarginBottom](../../aspose.words.drawing/textbox/internalmarginbottom/) { get; set; } | Especifica el margen inferior interior en puntos para una forma. |
| [InternalMarginLeft](../../aspose.words.drawing/textbox/internalmarginleft/) { get; set; } | Especifica el margen interior izquierdo en puntos para una forma. |
| [InternalMarginRight](../../aspose.words.drawing/textbox/internalmarginright/) { get; set; } | Especifica el margen interior derecho en puntos para una forma. |
| [InternalMarginTop](../../aspose.words.drawing/textbox/internalmargintop/) { get; set; } | Especifica el margen superior interior en puntos para una forma. |
| [LayoutFlow](../../aspose.words.drawing/textbox/layoutflow/) { get; set; } | Determina el flujo del diseño del texto en una forma. |
| [Next](../../aspose.words.drawing/textbox/next/) { get; set; } | Devuelve o establece un TextBox que representa el siguiente TextBox en una secuencia de formas. |
| [Parent](../../aspose.words.drawing/textbox/parent/) { get; } | Obtiene una forma principal para TextBox. |
| [Previous](../../aspose.words.drawing/textbox/previous/) { get; } | Devuelve un TextBox que representa el TextBox anterior en una secuencia de formas. |
| [TextBoxWrapMode](../../aspose.words.drawing/textbox/textboxwrapmode/) { get; set; } | Determina cómo se ajusta el texto dentro de una forma. |
| [VerticalAnchor](../../aspose.words.drawing/textbox/verticalanchor/) { get; set; } | Especifica la alineación vertical del texto dentro de una forma. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [BreakForwardLink](../../aspose.words.drawing/textbox/breakforwardlink/)() | Rompe el enlace al siguiente TextBox. |
| [IsValidLinkTarget](../../aspose.words.drawing/textbox/isvalidlinktarget/)(TextBox) | Determina si este cuadro de texto se puede vincular al cuadro de texto de destino. |

### Observaciones

Utilizar el[`TextBox`](../shape/textbox/) propiedad para acceder a las propiedades de texto de una forma. No crea instancias de la`TextBox` clase directamente.

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

Muestra cómo hacer que un cuadro de texto cambie de tamaño para que se ajuste perfectamente a su contenido.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Aplicar estos valores a ambos miembros para que la forma principal se ajuste
// estrechamente alrededor del contenido del texto, ignorando las dimensiones que hemos establecido.
textBox.FitShapeToText = true;
textBox.TextBoxWrapMode = TextBoxWrapMode.None;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text fit tightly inside textbox.");

doc.Save(ArtifactsDir + "Shape.TextBoxFitShapeToText.docx");
```

### Ver también

* espacio de nombres [Aspose.Words.Drawing](../../aspose.words.drawing/)
* asamblea [Aspose.Words](../../)


