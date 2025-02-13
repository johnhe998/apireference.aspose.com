---
title: ShapeBase.Top
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Получает или задает положение верхнего края содержащего блока фигуры.
type: docs
weight: 500
url: /ru/net/aspose.words.drawing/shapebase/top/
---
## ShapeBase.Top property

Получает или задает положение верхнего края содержащего блока фигуры.

```csharp
public double Top { get; set; }
```

### Примечания

Для формы верхнего уровня значение указывается в пунктах и относительно привязки формы.

Для фигур в группе значение находится в пространстве координат и единицах родительской группы.

Значение по умолчанию — 0.

Имеет эффект только для плавающих фигур.

### Примеры

Показывает, как вставить плавающее изображение и указать его положение и размер.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;

// Настройте свойство "RelativeHorizontalPosition" фигуры для обработки значения свойства "Left"
 // как горизонтальное расстояние фигуры в пунктах от левой стороны страницы.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;

// Установить горизонтальное расстояние фигуры от левой стороны страницы до 100.
shape.Left = 100;

// Аналогичным образом используйте свойство «RelativeVerticalPosition», чтобы расположить фигуру на 80 пунктов ниже верхнего края страницы.
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Top = 80;

// Установите высоту фигуры, которая автоматически масштабирует ширину для сохранения размеров.
shape.Height = 125;

Assert.AreEqual(125.0d, shape.Width);

// Свойства "Нижний" и "Правый" содержат нижний и правый края изображения.
Assert.AreEqual(shape.Top + shape.Height, shape.Bottom);
Assert.AreEqual(shape.Left + shape.Width, shape.Right);

doc.Save(ArtifactsDir + "Image.CreateFloatingPositionSize.docx");
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


