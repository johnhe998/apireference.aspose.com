---
title: ShapeBase.LocalToParent
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase метод. Преобразует значение из локального координатного пространства в координатное пространство родительской фигуры.
type: docs
weight: 610
url: /ru/net/aspose.words.drawing/shapebase/localtoparent/
---
## ShapeBase.LocalToParent method

Преобразует значение из локального координатного пространства в координатное пространство родительской фигуры.

```csharp
public PointF LocalToParent(PointF value)
```

### Примеры

Показывает, как преобразовать расположение координат x и y на координатной плоскости фигуры в положение на координатной плоскости родительской фигуры.

```csharp
Document doc = new Document();

// Вставьте фигуру группы и поместите ее на 100 пунктов ниже и правее
// исходная точка координат X и Y документа.
GroupShape group = new GroupShape(doc);
group.Bounds = new RectangleF(100, 100, 500, 500);

// Используйте метод "LocalToParent", чтобы определить, что (0, 0) во внутренних координатах x и y группы
// лежит на (100, 100) системы координат родительской формы. Родителем фигуры группы является сам документ.
Assert.AreEqual(new PointF(100, 100), group.LocalToParent(new PointF(0, 0)));

// По умолчанию внутренняя координатная плоскость фигуры имеет верхний левый угол в точке (0, 0),
// и нижний правый угол на (1000, 1000). Из-за своего размера форма нашей группы занимает площадь 500 x 500 пикселей.
// в плоскости документа. Это означает, что перемещение на 1 точку в координатной плоскости документа будет переводить
// к перемещению на 2 точки на координатной плоскости формы группы.
Assert.AreEqual(new PointF(150, 150), group.LocalToParent(new PointF(100, 100)));
Assert.AreEqual(new PointF(200, 200), group.LocalToParent(new PointF(200, 200)));
Assert.AreEqual(new PointF(250, 250), group.LocalToParent(new PointF(300, 300)));

// Переместите начало оси x и y формы группы из верхнего левого угла в центр.
// Это еще больше сместит внутренние координаты группы относительно координат документа.
group.CoordOrigin = new Point(-250, -250);

Assert.AreEqual(new PointF(375, 375), group.LocalToParent(new PointF(300, 300)));

// Изменение масштаба координатной плоскости также повлияет на относительные местоположения.
group.CoordSize = new Size(500, 500);

Assert.AreEqual(new PointF(650, 650), group.LocalToParent(new PointF(300, 300)));

// Если мы хотим добавить фигуру в эту группу, определяя ее местоположение на основе местоположения в документе,
// нам нужно будет сначала подтвердить местоположение в форме группы, которое будет соответствовать местоположению документа.
Assert.AreEqual(new PointF(700, 700), group.LocalToParent(new PointF(350, 350)));

Shape shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 700,
    Top = 700
};

group.AppendChild(shape);
doc.FirstSection.Body.FirstParagraph.AppendChild(group);

doc.Save(ArtifactsDir + "Shape.LocalToParent.docx");
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


