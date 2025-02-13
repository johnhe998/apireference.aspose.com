---
title: Fill.Opacity
second_title: Справочник по API Aspose.Words для .NET
description: Fill свойство. Получает или задает степень непрозрачности указанной заливки в виде значения от 00 прозрачная до 10 непрозрачная.
type: docs
weight: 90
url: /ru/net/aspose.words.drawing/fill/opacity/
---
## Fill.Opacity property

Получает или задает степень непрозрачности указанной заливки в виде значения от 0,0 (прозрачная) до 1,0 (непрозрачная).

```csharp
public double Opacity { get; set; }
```

### Примечания

Это свойство противоположно свойству[`Transparency`](../transparency/).

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

* class [Fill](../)
* пространство имен [Aspose.Words.Drawing](../../fill/)
* сборка [Aspose.Words](../../../)


