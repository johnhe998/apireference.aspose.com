---
title: Class TextBox
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.TextBox klas. Definiert Attribute die angeben wie ein Text in einer Form angezeigt wird.
type: docs
weight: 1170
url: /de/net/aspose.words.drawing/textbox/
---
## TextBox class

Definiert Attribute, die angeben, wie ein Text in einer Form angezeigt wird.

```csharp
public class TextBox
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [FitShapeToText](../../aspose.words.drawing/textbox/fitshapetotext/) { get; set; } | Legt fest, ob Microsoft Word die Form vergrößert, damit sie in den Text passt. |
| [InternalMarginBottom](../../aspose.words.drawing/textbox/internalmarginbottom/) { get; set; } | Gibt den inneren unteren Rand in Punkt für eine Form an. |
| [InternalMarginLeft](../../aspose.words.drawing/textbox/internalmarginleft/) { get; set; } | Gibt den inneren linken Rand in Punkt für eine Form an. |
| [InternalMarginRight](../../aspose.words.drawing/textbox/internalmarginright/) { get; set; } | Gibt den inneren rechten Rand in Punkt für eine Form an. |
| [InternalMarginTop](../../aspose.words.drawing/textbox/internalmargintop/) { get; set; } | Gibt den inneren oberen Rand in Punkten für eine Form an. |
| [LayoutFlow](../../aspose.words.drawing/textbox/layoutflow/) { get; set; } | Bestimmt den Fluss des Textlayouts in einer Form. |
| [Next](../../aspose.words.drawing/textbox/next/) { get; set; } | Gibt eine TextBox zurück oder legt sie fest, die die nächste TextBox in einer Folge von Formen darstellt. |
| [Parent](../../aspose.words.drawing/textbox/parent/) { get; } | Ruft eine übergeordnete Form für die TextBox ab. |
| [Previous](../../aspose.words.drawing/textbox/previous/) { get; } | Gibt eine TextBox zurück, die die vorherige TextBox in einer Folge von Formen darstellt. |
| [TextBoxWrapMode](../../aspose.words.drawing/textbox/textboxwrapmode/) { get; set; } | Legt fest, wie Text innerhalb einer Form umbrochen wird. |
| [VerticalAnchor](../../aspose.words.drawing/textbox/verticalanchor/) { get; set; } | Gibt die vertikale Ausrichtung des Textes innerhalb einer Form an. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [BreakForwardLink](../../aspose.words.drawing/textbox/breakforwardlink/)() | Unterbricht den Link zur nächsten TextBox. |
| [IsValidLinkTarget](../../aspose.words.drawing/textbox/isvalidlinktarget/)(TextBox) | Legt fest, ob diese TextBox mit der Ziel-Textbox verknüpft werden kann. |

### Bemerkungen

Verwenden Sie die[`TextBox`](../shape/textbox/) -Eigenschaft, um auf die Texteigenschaften einer Form zuzugreifen. Sie erstellen keine Instanzen der`TextBox` Klasse direkt.

### Beispiele

Zeigt, wie interne Ränder für ein Textfeld festgelegt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein weiteres Textfeld mit bestimmten Rändern ein.
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

Zeigt, wie die Ausrichtung von Text in einem Textfeld festgelegt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Verschieben Sie den Document Builder in die TextBox und fügen Sie Text hinzu.
builder.MoveTo(textBoxShape.LastParagraph);
builder.Writeln("Hello world!");
builder.Write("Hello again!");

// Legen Sie die Eigenschaft "LayoutFlow" fest, um eine Ausrichtung für den Textinhalt dieses Textfelds festzulegen.
textBox.LayoutFlow = layoutFlow;

doc.Save(ArtifactsDir + "Shape.TextBoxLayoutFlow.docx");
```

Zeigt, wie ein Textfeld dazu gebracht wird, seine Größe so zu ändern, dass es eng an seinen Inhalt passt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Wenden Sie diese Werte auf diese beiden Elemente an, damit die übergeordnete Form passt
// eng um den Textinhalt herum und ignoriert die von uns festgelegten Abmessungen.
textBox.FitShapeToText = true;
textBox.TextBoxWrapMode = TextBoxWrapMode.None;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text fit tightly inside textbox.");

doc.Save(ArtifactsDir + "Shape.TextBoxFitShapeToText.docx");
```

### Siehe auch

* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


