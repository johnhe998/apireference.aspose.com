---
title: NodeCollection.ToArray
second_title: Aspose.Words för .NET API Referens
description: NodeCollection metod. Kopierar alla noder från samlingen till en ny array av noder.
type: docs
weight: 110
url: /sv/net/aspose.words/nodecollection/toarray/
---
## NodeCollection.ToArray method

Kopierar alla noder från samlingen till en ny array av noder.

```csharp
public Node[] ToArray()
```

### Returvärde

En rad noder.

### Anmärkningar

Du bör inte lägga till/ta bort noder medan du itererar över en samling av noder eftersom det ogiltigförklarar iteratorn och kräver uppdateringar för livesamlingar.

För att kunna lägga till/ta bort noder under iteration, använd den här metoden för att kopiera noder till en array med fast storlek och sedan iterera över arrayen.

### Exempel

Visar hur man ersätter alla textruteformer med bildformer.

```csharp
Document doc = new Document(MyDir + "Textboxes in drawing canvas.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(3, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(1, shapes.Count(s => s.ShapeType == ShapeType.Image));

foreach (Shape shape in shapes)
{
    if (shape.ShapeType == ShapeType.TextBox)
    {
        Shape replacementShape = new Shape(doc, ShapeType.Image);
        replacementShape.ImageData.SetImage(ImageDir + "Logo.jpg");
        replacementShape.Left = shape.Left;
        replacementShape.Top = shape.Top;
        replacementShape.Width = shape.Width;
        replacementShape.Height = shape.Height;
        replacementShape.RelativeHorizontalPosition = shape.RelativeHorizontalPosition;
        replacementShape.RelativeVerticalPosition = shape.RelativeVerticalPosition;
        replacementShape.HorizontalAlignment = shape.HorizontalAlignment;
        replacementShape.VerticalAlignment = shape.VerticalAlignment;
        replacementShape.WrapType = shape.WrapType;
        replacementShape.WrapSide = shape.WrapSide;

        shape.ParentNode.InsertAfter(replacementShape, shape);
        shape.Remove();
    }
}

shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(0, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(4, shapes.Count(s => s.ShapeType == ShapeType.Image));

doc.Save(ArtifactsDir + "Shape.ReplaceTextboxesWithImages.docx");
```

### Se även

* class [Node](../../node/)
* class [NodeCollection](../)
* namnutrymme [Aspose.Words](../../nodecollection/)
* hopsättning [Aspose.Words](../../../)


