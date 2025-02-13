---
title: ShapeBase.IsDeleteRevision
second_title: Aspose.Words för .NET API Referens
description: ShapeBase fast egendom. Returnerar sant om detta objekt raderades i Microsoft Word medan ändringsspårning var aktiverad.
type: docs
weight: 240
url: /sv/net/aspose.words.drawing/shapebase/isdeleterevision/
---
## ShapeBase.IsDeleteRevision property

Returnerar sant om detta objekt raderades i Microsoft Word medan ändringsspårning var aktiverad.

```csharp
public bool IsDeleteRevision { get; }
```

### Exempel

Visar hur man arbetar med revideringsformer.

```csharp
Document doc = new Document();

Assert.False(doc.TrackRevisions);

// Infoga en inline-form utan att spåra revisioner, vilket gör att denna form inte är en revision av något slag.
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Börja spåra revisioner och infoga sedan en annan form, som kommer att bli en revision.
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

shapes[0].Remove();

// Eftersom vi tog bort den formen medan vi spårade ändringar,
// formen finns kvar i dokumentet och räknas som en raderingsrevision.
// Om du accepterar denna version kommer formen att tas bort permanent, och om du avvisar den kommer den att behållas i dokumentet.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Och vi infogade en annan form medan vi spårade ändringar, så den formen kommer att räknas som en insättningsrevision.
// Om du accepterar den här revideringen kommer den här formen att assimileras i dokumentet som en icke-revision,
// och att avvisa revisionen kommer att ta bort denna form permanent.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

### Se även

* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


