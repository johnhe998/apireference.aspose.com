---
title: ShapeBase.IsDecorative
second_title: Aspose.Words för .NET API Referens
description: ShapeBase fast egendom. Hämtar eller ställer in flaggan som anger om formen är dekorativ i dokumentet.
type: docs
weight: 230
url: /sv/net/aspose.words.drawing/shapebase/isdecorative/
---
## ShapeBase.IsDecorative property

Hämtar eller ställer in flaggan som anger om formen är dekorativ i dokumentet.

```csharp
public bool IsDecorative { get; set; }
```

### Anmärkningar

Observera att formen inte är tom[`AlternativeText`](../alternativetext/) kan inte vara dekorativ.

### Exempel

Visar hur man ställer in att formen är dekorativ.

```csharp
Document doc = new Document(MyDir + "Decorative shapes.docx");

Shape shape = (Shape) doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(shape.IsDecorative);

// Om "Alternativ text" inte är tom kan formen inte vara dekorativ.
// Det är därför vårt värde har ändrats till "falskt".
shape.AlternativeText = "Alternative text.";
Assert.False(shape.IsDecorative);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
// Skapa en ny form som dekorativ.
shape = builder.InsertShape(ShapeType.Rectangle, 100, 100);
shape.IsDecorative = true;

doc.Save(ArtifactsDir + "Shape.IsDecorative.docx");
```

### Se även

* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


