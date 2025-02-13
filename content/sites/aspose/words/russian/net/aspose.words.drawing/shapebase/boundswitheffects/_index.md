---
title: ShapeBase.BoundsWithEffects
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Получает окончательный размер который имеет этот объект формы после применения эффектов рисования. Значение измеряется в пунктах.
type: docs
weight: 90
url: /ru/net/aspose.words.drawing/shapebase/boundswitheffects/
---
## ShapeBase.BoundsWithEffects property

Получает окончательный размер, который имеет этот объект формы после применения эффектов рисования. Значение измеряется в пунктах.

```csharp
public RectangleF BoundsWithEffects { get; }
```

### Примеры

Показывает, как проверить, как на границы фигуры влияют эффекты формы.

```csharp
Document doc = new Document(MyDir + "Shape shadow effect.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// Эти две фигуры идентичны с точки зрения размеров и типа формы.
Assert.AreEqual(shapes[0].Width, shapes[1].Width);
Assert.AreEqual(shapes[0].Height, shapes[1].Height);
Assert.AreEqual(shapes[0].ShapeType, shapes[1].ShapeType);

// Первая фигура не имеет эффектов, а вторая имеет тень и толстый контур.
// Эти эффекты делают размер силуэта второй фигуры больше, чем у первой.
// Несмотря на то, что размер прямоугольника отображается, когда мы нажимаем на эти фигуры в Microsoft Word,
// на видимые внешние границы второй фигуры влияют тень и контур, и поэтому они больше.
// Мы можем использовать метод "AdjustWithEffects", чтобы увидеть истинный размер фигуры.
Assert.AreEqual(0.0, shapes[0].StrokeWeight);
Assert.AreEqual(20.0, shapes[1].StrokeWeight);
Assert.False(shapes[0].ShadowEnabled);
Assert.True(shapes[1].ShadowEnabled);

Shape shape = shapes[0];

// Создаем объект RectangleF, представляющий прямоугольник,
// которые мы потенциально могли бы использовать в качестве координат и границ фигуры.
RectangleF rectangleF = new RectangleF(200, 200, 1000, 1000);

// Запустите этот метод, чтобы настроить размер прямоугольника для всех наших эффектов формы.
RectangleF rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Поскольку форма не имеет эффектов изменения границ, ее граничные размеры не затрагиваются.
Assert.AreEqual(200, rectangleFOut.X);
Assert.AreEqual(200, rectangleFOut.Y);
Assert.AreEqual(1000, rectangleFOut.Width);
Assert.AreEqual(1000, rectangleFOut.Height);

// Проверяем окончательный размер первой фигуры в точках.
Assert.AreEqual(0, shape.BoundsWithEffects.X);
Assert.AreEqual(0, shape.BoundsWithEffects.Y);
Assert.AreEqual(147, shape.BoundsWithEffects.Width);
Assert.AreEqual(147, shape.BoundsWithEffects.Height);

shape = shapes[1];
rectangleF = new RectangleF(200, 200, 1000, 1000);
rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Эффекты формы немного сдвинули кажущийся верхний левый угол фигуры.
Assert.AreEqual(171.5, rectangleFOut.X);
Assert.AreEqual(167, rectangleFOut.Y);

// Эффекты также повлияли на видимые размеры фигуры.
Assert.AreEqual(1045, rectangleFOut.Width);
Assert.AreEqual(1132, rectangleFOut.Height);

// Эффекты также повлияли на видимые границы фигуры.
Assert.AreEqual(-28.5, shape.BoundsWithEffects.X);
Assert.AreEqual(-33, shape.BoundsWithEffects.Y);
Assert.AreEqual(192, shape.BoundsWithEffects.Width);
Assert.AreEqual(279, shape.BoundsWithEffects.Height);
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


