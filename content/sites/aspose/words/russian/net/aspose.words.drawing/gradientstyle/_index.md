---
title: Enum GradientStyle
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.GradientStyle перечисление. Определяет стиль градиентной заливки.
type: docs
weight: 870
url: /ru/net/aspose.words.drawing/gradientstyle/
---
## GradientStyle enumeration

Определяет стиль градиентной заливки.

```csharp
public enum GradientStyle
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `-1` | Нет градиента. |
| Horizontal | `1` | Градиент проходит горизонтально через объект. |
| Vertical | `2` | Градиент, идущий вертикально вниз по объекту. |
| DiagonalUp | `3` | Диагональный градиент, движущийся от нижнего угла вверх к противоположному углу. |
| DiagonalDown | `4` | Диагональный градиент, движущийся от верхнего угла вниз к противоположному углу. |
| FromCorner | `5` | Градиент от угла к трем другим углам. |
| FromCenter | `6` | Градиент от центра к углам. |

### Примеры

Показывает, как заполнить фигуру градиентами.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// Применяем одноцветную градиентную заливку к фигуре с ForeColor градиентной заливки.
shape.Fill.OneColorGradient(Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2, 0.1);

Assert.AreEqual(Color.Red.ToArgb(), shape.Fill.ForeColor.ToArgb());
Assert.AreEqual(GradientStyle.Horizontal, shape.Fill.GradientStyle);
Assert.AreEqual(GradientVariant.Variant2, shape.Fill.GradientVariant);
Assert.AreEqual(270, shape.Fill.GradientAngle);

shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// Применяем к фигуре заливку двухцветным градиентом.
shape.Fill.TwoColorGradient(GradientStyle.FromCorner, GradientVariant.Variant4);
// Изменяем BackColor градиентной заливки.
shape.Fill.BackColor = Color.Yellow;
// Обратите внимание, что "GradientAngle" заменяется на "GradientStyle.FromCorner/GradientStyle.FromCenter"
// градиентная заливка не дает никакого эффекта, она будет работать только для линейного градиента.
shape.Fill.GradientAngle = 15;

Assert.AreEqual(Color.Yellow.ToArgb(), shape.Fill.BackColor.ToArgb());
Assert.AreEqual(GradientStyle.FromCorner, shape.Fill.GradientStyle);
Assert.AreEqual(GradientVariant.Variant4, shape.Fill.GradientVariant);
Assert.AreEqual(0, shape.Fill.GradientAngle);

// Используйте параметр соответствия для определения формы с помощью DML, если вы хотите получить "GradientStyle",
// Свойства "GradientVariant" и "GradientAngle" после сохранения документа.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientFill.docx", saveOptions);
```

### Смотрите также

* пространство имен [Aspose.Words.Drawing](../../aspose.words.drawing/)
* сборка [Aspose.Words](../../)


