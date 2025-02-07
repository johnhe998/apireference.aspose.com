---
title: ShapeBase.BoundsInPoints
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Получает расположение и размер содержащего блока фигуры в пунктах относительно привязки самой верхней фигуры.
type: docs
weight: 80
url: /ru/net/aspose.words.drawing/shapebase/boundsinpoints/
---
## ShapeBase.BoundsInPoints property

Получает расположение и размер содержащего блока фигуры в пунктах относительно привязки самой верхней фигуры.

```csharp
public RectangleF BoundsInPoints { get; }
```

### Примеры

Показывает, как проверить форму, содержащую границы блоков.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Line, RelativeHorizontalPosition.LeftMargin, 50,
    RelativeVerticalPosition.TopMargin, 50, 100, 100, WrapType.None);
shape.StrokeColor = Color.Orange;

// Несмотря на то, что сама строка занимает мало места на странице документа,
// он занимает прямоугольный содержащий блок, размер которого мы можем определить с помощью свойств "Границы".
Assert.AreEqual(new RectangleF(50, 50, 100, 100), shape.Bounds);
Assert.AreEqual(new RectangleF(50, 50, 100, 100), shape.BoundsInPoints);

// Создайте фигуру группы, а затем установите размер содержащего ее блока с помощью свойства «Границы».
GroupShape group = new GroupShape(doc);
group.Bounds = new RectangleF(0, 100, 250, 250);

Assert.AreEqual(new RectangleF(0, 100, 250, 250), group.BoundsInPoints);

// Создайте прямоугольник, проверьте размер его ограничивающего блока, а затем добавьте его к фигуре группы.
shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 700,
    Top = 700
};

Assert.AreEqual(new RectangleF(700, 700, 100, 100), shape.BoundsInPoints);

group.AppendChild(shape);

// Координатная плоскость групповой формы имеет начало в верхнем левом углу содержащего ее блока,
// и координаты x и y (1000, 1000) в правом нижнем углу.
// Наша фигура группы имеет размер 250x250 точек, поэтому каждые 4 точки на координатной плоскости формы группы
// преобразуется в 1 точку в координатной плоскости тела документа.
// Каждая фигура, которую мы вставляем, также уменьшается в размере в 4 раза.
// Это отразится на изменении свойства "BoundsInPoints" фигуры.
Assert.AreEqual(new RectangleF(175, 275, 25, 25), shape.BoundsInPoints);

doc.FirstSection.Body.FirstParagraph.AppendChild(group);

// Вставьте фигуру и поместите ее за пределы блока, содержащего фигуру группы.
shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 1000,
    Top = 1000
};

group.AppendChild(shape);

// Размер фигуры группы в теле документа увеличился, но содержащий ее блок остался прежним.
Assert.AreEqual(new RectangleF(0, 100, 250, 250), group.BoundsInPoints);
Assert.AreEqual(new RectangleF(250, 350, 25, 25), shape.BoundsInPoints);

doc.Save(ArtifactsDir + "Shape.Bounds.docx");
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


