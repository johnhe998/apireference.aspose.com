---
title: ShapeBase.AdjustWithEffects
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase methode. Addiert die Quellrechteckwerte der Effektausdehnung und gibt das endgültige Rechteck zurück.
type: docs
weight: 560
url: /de/net/aspose.words.drawing/shapebase/adjustwitheffects/
---
## ShapeBase.AdjustWithEffects method

Addiert die Quellrechteckwerte der Effektausdehnung und gibt das endgültige Rechteck zurück.

```csharp
public RectangleF AdjustWithEffects(RectangleF source)
```

### Beispiele

Zeigt, wie Sie überprüfen können, wie die Begrenzungen einer Form von Formeffekten beeinflusst werden.

```csharp
Document doc = new Document(MyDir + "Shape shadow effect.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// Die beiden Formen sind in Bezug auf Abmessungen und Formtyp identisch.
Assert.AreEqual(shapes[0].Width, shapes[1].Width);
Assert.AreEqual(shapes[0].Height, shapes[1].Height);
Assert.AreEqual(shapes[0].ShapeType, shapes[1].ShapeType);

// Die erste Form hat keine Effekte und die zweite hat einen Schatten und einen dicken Umriss.
// Diese Effekte machen die Silhouette der zweiten Form größer als die der ersten.
// Obwohl die Größe des Rechtecks angezeigt wird, wenn wir auf diese Formen in Microsoft Word klicken,
// Die sichtbaren äußeren Grenzen der zweiten Form werden von Schatten und Umriss beeinflusst und sind daher größer.
// Wir können die "AdjustWithEffects"-Methode verwenden, um die wahre Größe der Form zu sehen.
Assert.AreEqual(0.0, shapes[0].StrokeWeight);
Assert.AreEqual(20.0, shapes[1].StrokeWeight);
Assert.False(shapes[0].ShadowEnabled);
Assert.True(shapes[1].ShadowEnabled);

Shape shape = shapes[0];

// Erstellen Sie ein RectangleF-Objekt, das ein Rechteck darstellt,
// die wir möglicherweise als Koordinaten und Grenzen für eine Form verwenden könnten.
RectangleF rectangleF = new RectangleF(200, 200, 1000, 1000);

// Führen Sie diese Methode aus, um die Größe des Rechtecks für alle unsere Formeffekte anzupassen.
RectangleF rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Da die Form keine Randveränderungseffekte hat, bleiben ihre Randabmessungen unbeeinflusst.
Assert.AreEqual(200, rectangleFOut.X);
Assert.AreEqual(200, rectangleFOut.Y);
Assert.AreEqual(1000, rectangleFOut.Width);
Assert.AreEqual(1000, rectangleFOut.Height);

// Überprüfen Sie die endgültige Ausdehnung der ersten Form in Punkten.
Assert.AreEqual(0, shape.BoundsWithEffects.X);
Assert.AreEqual(0, shape.BoundsWithEffects.Y);
Assert.AreEqual(147, shape.BoundsWithEffects.Width);
Assert.AreEqual(147, shape.BoundsWithEffects.Height);

shape = shapes[1];
rectangleF = new RectangleF(200, 200, 1000, 1000);
rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Die Formeffekte haben die sichtbare obere linke Ecke der Form leicht verschoben.
Assert.AreEqual(171.5, rectangleFOut.X);
Assert.AreEqual(167, rectangleFOut.Y);

// Die Effekte haben sich auch auf die sichtbaren Abmessungen der Form ausgewirkt.
Assert.AreEqual(1045, rectangleFOut.Width);
Assert.AreEqual(1132, rectangleFOut.Height);

// Die Effekte haben auch die sichtbaren Grenzen der Form beeinflusst.
Assert.AreEqual(-28.5, shape.BoundsWithEffects.X);
Assert.AreEqual(-33, shape.BoundsWithEffects.Y);
Assert.AreEqual(192, shape.BoundsWithEffects.Width);
Assert.AreEqual(279, shape.BoundsWithEffects.Height);
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


