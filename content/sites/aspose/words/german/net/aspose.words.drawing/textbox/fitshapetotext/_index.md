---
title: TextBox.FitShapeToText
second_title: Aspose.Words für .NET-API-Referenz
description: TextBox eigendom. Legt fest ob Microsoft Word die Form vergrößert damit sie in den Text passt.
type: docs
weight: 10
url: /de/net/aspose.words.drawing/textbox/fitshapetotext/
---
## TextBox.FitShapeToText property

Legt fest, ob Microsoft Word die Form vergrößert, damit sie in den Text passt.

```csharp
public bool FitShapeToText { get; set; }
```

### Bemerkungen

Der Standardwert ist **FALSCH**.

### Beispiele

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

* class [TextBox](../)
* namensraum [Aspose.Words.Drawing](../../textbox/)
* Montage [Aspose.Words](../../../)


