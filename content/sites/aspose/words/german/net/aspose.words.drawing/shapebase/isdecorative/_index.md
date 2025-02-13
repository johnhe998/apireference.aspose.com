---
title: ShapeBase.IsDecorative
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Ruft das Flag ab oder setzt es das angibt ob die Form im Dokument dekorativ ist.
type: docs
weight: 230
url: /de/net/aspose.words.drawing/shapebase/isdecorative/
---
## ShapeBase.IsDecorative property

Ruft das Flag ab oder setzt es, das angibt, ob die Form im Dokument dekorativ ist.

```csharp
public bool IsDecorative { get; set; }
```

### Bemerkungen

Beachten Sie, dass die Form nicht leer ist[`AlternativeText`](../alternativetext/) kann nicht dekorativ sein.

### Beispiele

Zeigt, wie Sie festlegen, dass die Form dekorativ ist.

```csharp
Document doc = new Document(MyDir + "Decorative shapes.docx");

Shape shape = (Shape) doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(shape.IsDecorative);

// Wenn "AlternativeText" nicht leer ist, kann die Form nicht dekorativ sein.
// Deshalb hat sich unser Wert auf 'false' geändert.
shape.AlternativeText = "Alternative text.";
Assert.False(shape.IsDecorative);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
// Erstellen Sie eine neue Form als Dekoration.
shape = builder.InsertShape(ShapeType.Rectangle, 100, 100);
shape.IsDecorative = true;

doc.Save(ArtifactsDir + "Shape.IsDecorative.docx");
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


