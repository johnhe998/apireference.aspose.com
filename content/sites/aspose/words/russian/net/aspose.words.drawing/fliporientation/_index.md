---
title: Enum FlipOrientation
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.FlipOrientation перечисление. Возможные значения для ориентации фигуры.
type: docs
weight: 840
url: /ru/net/aspose.words.drawing/fliporientation/
---
## FlipOrientation enumeration

Возможные значения для ориентации фигуры.

```csharp
[Flags]
public enum FlipOrientation
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Координаты не переворачиваются. |
| Horizontal | `1` | Отразить по оси Y, поменяв координаты x на противоположные. |
| Vertical | `2` | Отразить по оси x, поменяв местами координаты y. |
| Both | `3` | Отразить по осям Y и X. |

### Примеры

Показывает, как отразить фигуру на оси.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте фигуру изображения и оставьте ее ориентацию в состоянии по умолчанию.
Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

Assert.AreEqual(FlipOrientation.None, shape.FlipOrientation);

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 250,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Установите для свойства "FlipOrientation" значение "FlipOrientation.Horizontal", чтобы отразить вторую фигуру по оси Y,
// превращаем его в горизонтальное зеркальное отображение первой формы.
shape.FlipOrientation = FlipOrientation.Horizontal;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 250, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Установите для свойства "FlipOrientation" значение "FlipOrientation.Horizontal", чтобы перевернуть третью фигуру по оси X,
// превращаем его в вертикальное зеркальное отображение первой формы.
shape.FlipOrientation = FlipOrientation.Vertical;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 250,
    RelativeVerticalPosition.TopMargin, 250, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// Установите для свойства "FlipOrientation" значение "FlipOrientation.Horizontal", чтобы отразить четвертую фигуру по обеим осям x и y,
// превращаем его в горизонтальное и вертикальное зеркальное отображение первой фигуры.
shape.FlipOrientation = FlipOrientation.Both;

doc.Save(ArtifactsDir + "Shape.FlipShapeOrientation.docx");
```

### Смотрите также

* property [FlipOrientation](../shapebase/fliporientation/)
* пространство имен [Aspose.Words.Drawing](../../aspose.words.drawing/)
* сборка [Aspose.Words](../../)


