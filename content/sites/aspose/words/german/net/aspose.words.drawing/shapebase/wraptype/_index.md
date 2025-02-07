---
title: ShapeBase.WrapType
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Definiert ob die Form eingebettet oder schwebend ist. Für schwebende Formen definiert den Umbruchmodus für Text um die Form.
type: docs
weight: 540
url: /de/net/aspose.words.drawing/shapebase/wraptype/
---
## ShapeBase.WrapType property

Definiert, ob die Form eingebettet oder schwebend ist. Für schwebende Formen definiert den Umbruchmodus für Text um die Form.

```csharp
public WrapType WrapType { get; set; }
```

### Bemerkungen

Der Standardwert istNone.

Hat nur Auswirkungen auf Shapes der obersten Ebene.

### Beispiele

Zeigt, wie ein schwebendes Bild in der Mitte einer Seite eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein schwebendes Bild ein, das hinter dem überlappenden Text angezeigt wird, und richten Sie es an der Mitte der Seite aus.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

Zeigt, wie ein Textfeld erstellt und formatiert wird.

```csharp
Document doc = new Document();

// Erstellen Sie ein schwebendes Textfeld.
Shape textBox = new Shape(doc, ShapeType.TextBox);
textBox.WrapType = WrapType.None;
textBox.Height = 50;
textBox.Width = 200;

// Legen Sie die horizontale und vertikale Ausrichtung des Textes innerhalb der Form fest.
textBox.HorizontalAlignment = HorizontalAlignment.Center;
textBox.VerticalAlignment = VerticalAlignment.Top;

// Füge einen Absatz zum Textfeld hinzu und füge einen Textverlauf hinzu, der im Textfeld angezeigt wird.
textBox.AppendChild(new Paragraph(doc));
Paragraph para = textBox.FirstParagraph;
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;
Run run = new Run(doc);
run.Text = "Hello world!";
para.AppendChild(run);

doc.FirstSection.Body.FirstParagraph.AppendChild(textBox);

doc.Save(ArtifactsDir + "Shape.CreateTextBox.docx");
```

### Siehe auch

* enum [WrapType](../../wraptype/)
* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


