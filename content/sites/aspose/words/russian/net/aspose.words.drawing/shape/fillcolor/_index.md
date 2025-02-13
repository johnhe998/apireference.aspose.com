---
title: Shape.FillColor
second_title: Справочник по API Aspose.Words для .NET
description: Shape свойство. Определяет цвет кисти заполняющий замкнутый контур фигуры.
type: docs
weight: 40
url: /ru/net/aspose.words.drawing/shape/fillcolor/
---
## Shape.FillColor property

Определяет цвет кисти, заполняющий замкнутый контур фигуры.

```csharp
public Color FillColor { get; set; }
```

### Примечания

Это ярлык дляColor имущество.

Значение по умолчанию: White.

### Примеры

Показывает, как заполнить фигуру сплошным цветом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Напишите какой-нибудь текст, а затем накройте его плавающей фигурой.
builder.Font.Size = 32;
builder.Writeln("Hello world!");

Shape shape = builder.InsertShape(ShapeType.CloudCallout, RelativeHorizontalPosition.LeftMargin, 25,
    RelativeVerticalPosition.TopMargin, 25, 250, 150, WrapType.None);

// Используйте свойство "StrokeColor", чтобы установить цвет контура фигуры.
shape.StrokeColor = Color.CadetBlue;

// Используйте свойство "FillColor", чтобы задать цвет внутренней области фигуры.
shape.FillColor = Color.LightBlue;

// Свойство "Непрозрачность" определяет, насколько прозрачен цвет по шкале от 0 до 1,
// где 1 полностью непрозрачно, а 0 невидимо.
// Заливка фигуры по умолчанию полностью непрозрачна, поэтому мы не можем видеть текст, поверх которого находится эта фигура.
Assert.AreEqual(1.0d, shape.Fill.Opacity);

// Установите непрозрачность цвета заливки фигуры на более низкое значение, чтобы мы могли видеть текст под ним.
shape.Fill.Opacity = 0.3;

doc.Save(ArtifactsDir + "Shape.Fill.docx");
```

### Смотрите также

* class [Shape](../)
* пространство имен [Aspose.Words.Drawing](../../shape/)
* сборка [Aspose.Words](../../../)


