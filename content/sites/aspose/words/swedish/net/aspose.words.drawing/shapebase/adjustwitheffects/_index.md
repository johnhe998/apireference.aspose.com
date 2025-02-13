---
title: ShapeBase.AdjustWithEffects
second_title: Aspose.Words för .NET API Referens
description: ShapeBase metod. Lägger till källrektangelvärdena för effektomfattningen och returnerar den sista rektangeln.
type: docs
weight: 560
url: /sv/net/aspose.words.drawing/shapebase/adjustwitheffects/
---
## ShapeBase.AdjustWithEffects method

Lägger till källrektangelvärdena för effektomfattningen och returnerar den sista rektangeln.

```csharp
public RectangleF AdjustWithEffects(RectangleF source)
```

### Exempel

Visar hur du kontrollerar hur en forms gränser påverkas av formeffekter.

```csharp
Document doc = new Document(MyDir + "Shape shadow effect.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// De två formerna är identiska när det gäller dimensioner och formtyp.
Assert.AreEqual(shapes[0].Width, shapes[1].Width);
Assert.AreEqual(shapes[0].Height, shapes[1].Height);
Assert.AreEqual(shapes[0].ShapeType, shapes[1].ShapeType);

// Den första formen har inga effekter, och den andra har en skugga och en tjock kontur.
// Dessa effekter gör storleken på den andra formens siluett större än den första.
// Även om rektangelns storlek visas när vi klickar på dessa former i Microsoft Word,
// de synliga yttre gränserna för den andra formen påverkas av skuggan och konturen och är därför större.
// Vi kan använda metoden "AdjustWithEffects" för att se den verkliga storleken på formen.
Assert.AreEqual(0.0, shapes[0].StrokeWeight);
Assert.AreEqual(20.0, shapes[1].StrokeWeight);
Assert.False(shapes[0].ShadowEnabled);
Assert.True(shapes[1].ShadowEnabled);

Shape shape = shapes[0];

// Skapa ett RectangleF-objekt, som representerar en rektangel,
// som vi potentiellt skulle kunna använda som koordinater och gränser för en form.
RectangleF rectangleF = new RectangleF(200, 200, 1000, 1000);

// Kör den här metoden för att få storleken på rektangeln justerad för alla våra formeffekter.
RectangleF rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Eftersom formen inte har några gränsförändrande effekter påverkas dess gränsdimensioner opåverkade.
Assert.AreEqual(200, rectangleFOut.X);
Assert.AreEqual(200, rectangleFOut.Y);
Assert.AreEqual(1000, rectangleFOut.Width);
Assert.AreEqual(1000, rectangleFOut.Height);

// Verifiera den slutliga omfattningen av den första formen, i punkter.
Assert.AreEqual(0, shape.BoundsWithEffects.X);
Assert.AreEqual(0, shape.BoundsWithEffects.Y);
Assert.AreEqual(147, shape.BoundsWithEffects.Width);
Assert.AreEqual(147, shape.BoundsWithEffects.Height);

shape = shapes[1];
rectangleF = new RectangleF(200, 200, 1000, 1000);
rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Formeffekterna har flyttat det uppenbara övre vänstra hörnet av formen något.
Assert.AreEqual(171.5, rectangleFOut.X);
Assert.AreEqual(167, rectangleFOut.Y);

// Effekterna har också påverkat formens synliga dimensioner.
Assert.AreEqual(1045, rectangleFOut.Width);
Assert.AreEqual(1132, rectangleFOut.Height);

// Effekterna har också påverkat formens synliga gränser.
Assert.AreEqual(-28.5, shape.BoundsWithEffects.X);
Assert.AreEqual(-33, shape.BoundsWithEffects.Y);
Assert.AreEqual(192, shape.BoundsWithEffects.Width);
Assert.AreEqual(279, shape.BoundsWithEffects.Height);
```

### Se även

* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


