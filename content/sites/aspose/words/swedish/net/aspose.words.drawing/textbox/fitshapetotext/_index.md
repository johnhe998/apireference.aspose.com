---
title: TextBox.FitShapeToText
second_title: Aspose.Words för .NET API Referens
description: TextBox fast egendom. Avgör om Microsoft Word kommer att växa formen så att den passar text.
type: docs
weight: 10
url: /sv/net/aspose.words.drawing/textbox/fitshapetotext/
---
## TextBox.FitShapeToText property

Avgör om Microsoft Word kommer att växa formen så att den passar text.

```csharp
public bool FitShapeToText { get; set; }
```

### Anmärkningar

Standardvärdet är **falsk**.

### Exempel

Visar hur man får en textruta att ändra storlek på sig själv så att den passar innehållet tätt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Tillämpa dessa värden på båda dessa medlemmar för att få den överordnade formen att passa
// tätt runt textinnehållet, ignorera de dimensioner vi har angett.
textBox.FitShapeToText = true;
textBox.TextBoxWrapMode = TextBoxWrapMode.None;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text fit tightly inside textbox.");

doc.Save(ArtifactsDir + "Shape.TextBoxFitShapeToText.docx");
```

### Se även

* class [TextBox](../)
* namnutrymme [Aspose.Words.Drawing](../../textbox/)
* hopsättning [Aspose.Words](../../../)


