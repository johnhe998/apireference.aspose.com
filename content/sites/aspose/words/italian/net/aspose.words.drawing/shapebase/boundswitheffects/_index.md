---
title: ShapeBase.BoundsWithEffects
second_title: Aspose.Words per .NET API Reference
description: ShapeBase proprietà. Ottiene lestensione finale di questo oggetto forma dopo lapplicazione degli effetti di disegno. Il valore viene misurato in punti.
type: docs
weight: 90
url: /it/net/aspose.words.drawing/shapebase/boundswitheffects/
---
## ShapeBase.BoundsWithEffects property

Ottiene l'estensione finale di questo oggetto forma dopo l'applicazione degli effetti di disegno. Il valore viene misurato in punti.

```csharp
public RectangleF BoundsWithEffects { get; }
```

### Esempi

Mostra come controllare in che modo i limiti di una forma sono influenzati dagli effetti della forma.

```csharp
Document doc = new Document(MyDir + "Shape shadow effect.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// Le due forme sono identiche in termini di dimensioni e tipo di forma.
Assert.AreEqual(shapes[0].Width, shapes[1].Width);
Assert.AreEqual(shapes[0].Height, shapes[1].Height);
Assert.AreEqual(shapes[0].ShapeType, shapes[1].ShapeType);

// La prima forma non ha effetti e la seconda ha un'ombra e un contorno spesso.
// Questi effetti rendono la dimensione della sagoma della seconda forma più grande di quella della prima.
// Anche se le dimensioni del rettangolo vengono visualizzate quando facciamo clic su queste forme in Microsoft Word,
// i limiti esterni visibili della seconda forma sono influenzati dall'ombra e dal contorno e quindi sono più grandi.
// Possiamo usare il metodo "AdjustWithEffects" per vedere la vera dimensione della forma.
Assert.AreEqual(0.0, shapes[0].StrokeWeight);
Assert.AreEqual(20.0, shapes[1].StrokeWeight);
Assert.False(shapes[0].ShadowEnabled);
Assert.True(shapes[1].ShadowEnabled);

Shape shape = shapes[0];

// Crea un oggetto RectangleF, che rappresenta un rettangolo,
// che potremmo potenzialmente utilizzare come coordinate e limiti per una forma.
RectangleF rectangleF = new RectangleF(200, 200, 1000, 1000);

// Esegui questo metodo per regolare la dimensione del rettangolo per tutti i nostri effetti di forma.
RectangleF rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Poiché la forma non ha effetti di modifica del bordo, le sue dimensioni del contorno non vengono modificate.
Assert.AreEqual(200, rectangleFOut.X);
Assert.AreEqual(200, rectangleFOut.Y);
Assert.AreEqual(1000, rectangleFOut.Width);
Assert.AreEqual(1000, rectangleFOut.Height);

// Verifica l'estensione finale della prima forma, in punti.
Assert.AreEqual(0, shape.BoundsWithEffects.X);
Assert.AreEqual(0, shape.BoundsWithEffects.Y);
Assert.AreEqual(147, shape.BoundsWithEffects.Width);
Assert.AreEqual(147, shape.BoundsWithEffects.Height);

shape = shapes[1];
rectangleF = new RectangleF(200, 200, 1000, 1000);
rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Gli effetti della forma hanno spostato leggermente l'apparente angolo superiore sinistro della forma.
Assert.AreEqual(171.5, rectangleFOut.X);
Assert.AreEqual(167, rectangleFOut.Y);

// Gli effetti hanno influenzato anche le dimensioni visibili della forma.
Assert.AreEqual(1045, rectangleFOut.Width);
Assert.AreEqual(1132, rectangleFOut.Height);

// Gli effetti hanno influenzato anche i limiti visibili della forma.
Assert.AreEqual(-28.5, shape.BoundsWithEffects.X);
Assert.AreEqual(-33, shape.BoundsWithEffects.Y);
Assert.AreEqual(192, shape.BoundsWithEffects.Width);
Assert.AreEqual(279, shape.BoundsWithEffects.Height);
```

### Guarda anche

* class [ShapeBase](../)
* spazio dei nomi [Aspose.Words.Drawing](../../shapebase/)
* assemblea [Aspose.Words](../../../)


