---
title: ShapeBase.ParentParagraph
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Gibt den unmittelbar übergeordneten Absatz zurück.
type: docs
weight: 390
url: /de/net/aspose.words.drawing/shapebase/parentparagraph/
---
## ShapeBase.ParentParagraph property

Gibt den unmittelbar übergeordneten Absatz zurück.

```csharp
public Paragraph ParentParagraph { get; }
```

### Bemerkungen

Für untergeordnete Shapes eines Gruppen-Shapes und untergeordnete Shapes eines Office Math-Objekts wird immer null zurückgegeben.

### Beispiele

Zeigt, wie ein Textfeld eingefügt und die Schriftart seines Inhalts festgelegt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

Shape shape = builder.InsertShape(ShapeType.TextBox, 300, 50);
builder.MoveTo(shape.LastParagraph);
builder.Write("This text is inside the text box.");

// Setzen Sie die „Hidden“-Eigenschaft des „Font“-Objekts der Form auf „true“, um das Textfeld unsichtbar zu machen
// und reduzieren Sie den Platz, den es normalerweise einnehmen würde.
// Setzen Sie die "Hidden"-Eigenschaft des "Font"-Objekts der Form auf "false", um das Textfeld sichtbar zu lassen.
shape.Font.Hidden = hideShape;

// Wenn die Form sichtbar ist, ändern wir ihr Aussehen über das Schriftobjekt.
if (!hideShape)
{
    shape.Font.HighlightColor = Color.LightGray;
    shape.Font.Color = Color.Red;
    shape.Font.Underline = Underline.Dash;
}

// Den Builder aus dem Textfeld zurück in das Hauptdokument verschieben.
builder.MoveTo(shape.ParentParagraph);

builder.Writeln("\nThis text is outside the text box.");

doc.Save(ArtifactsDir + "Shape.Font.docx");
```

### Siehe auch

* class [Paragraph](../../../aspose.words/paragraph/)
* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


