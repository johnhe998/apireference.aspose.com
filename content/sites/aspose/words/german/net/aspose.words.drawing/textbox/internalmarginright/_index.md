---
title: TextBox.InternalMarginRight
second_title: Aspose.Words für .NET-API-Referenz
description: TextBox eigendom. Gibt den inneren rechten Rand in Punkt für eine Form an.
type: docs
weight: 40
url: /de/net/aspose.words.drawing/textbox/internalmarginright/
---
## TextBox.InternalMarginRight property

Gibt den inneren rechten Rand in Punkt für eine Form an.

```csharp
public double InternalMarginRight { get; set; }
```

### Bemerkungen

Der Standardwert ist 1/10 Zoll.

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

### Siehe auch

* class [TextBox](../)
* namensraum [Aspose.Words.Drawing](../../textbox/)
* Montage [Aspose.Words](../../../)


