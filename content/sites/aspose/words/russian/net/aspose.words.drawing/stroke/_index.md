---
title: Class Stroke
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.Stroke сорт. Определяет обводку фигуры.
type: docs
weight: 1160
url: /ru/net/aspose.words.drawing/stroke/
---
## Stroke class

Определяет обводку фигуры.

```csharp
public class Stroke
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [BackColor](../../aspose.words.drawing/stroke/backcolor/) { get; set; } | Получает или задает цвет фона обводки. |
| [Color](../../aspose.words.drawing/stroke/color/) { get; set; } | Определяет цвет обводки. |
| [Color2](../../aspose.words.drawing/stroke/color2/) { get; set; } | Определяет второй цвет обводки. |
| [DashStyle](../../aspose.words.drawing/stroke/dashstyle/) { get; set; } | Указывает образец точки и штриха для штриха. |
| [EndArrowLength](../../aspose.words.drawing/stroke/endarrowlength/) { get; set; } | Определяет длину стрелки для конца штриха. |
| [EndArrowType](../../aspose.words.drawing/stroke/endarrowtype/) { get; set; } | Определяет наконечник стрелки для конца штриха. |
| [EndArrowWidth](../../aspose.words.drawing/stroke/endarrowwidth/) { get; set; } | Определяет ширину наконечника стрелки для конца штриха. |
| [EndCap](../../aspose.words.drawing/stroke/endcap/) { get; set; } | Определяет стиль окончания штриха. |
| [ForeColor](../../aspose.words.drawing/stroke/forecolor/) { get; set; } | Получает или задает цвет переднего плана обводки. |
| [ImageBytes](../../aspose.words.drawing/stroke/imagebytes/) { get; } | Определяет изображение для штрихового изображения или заливки узором. |
| [JoinStyle](../../aspose.words.drawing/stroke/joinstyle/) { get; set; } | Определяет стиль соединения полилинии. |
| [LineStyle](../../aspose.words.drawing/stroke/linestyle/) { get; set; } | Определяет стиль линии штриха. |
| [On](../../aspose.words.drawing/stroke/on/) { get; set; } | Определяет, будет ли обведен контур. |
| [Opacity](../../aspose.words.drawing/stroke/opacity/) { get; set; } | Определяет степень прозрачности штриха. Допустимый диапазон от 0 до 1. |
| [StartArrowLength](../../aspose.words.drawing/stroke/startarrowlength/) { get; set; } | Определяет длину стрелки для начала штриха. |
| [StartArrowType](../../aspose.words.drawing/stroke/startarrowtype/) { get; set; } | Определяет наконечник стрелки для начала штриха. |
| [StartArrowWidth](../../aspose.words.drawing/stroke/startarrowwidth/) { get; set; } | Определяет ширину стрелки для начала штриха. |
| [Transparency](../../aspose.words.drawing/stroke/transparency/) { get; set; } | Получает или задает значение от 0,0 (непрозрачный) до 1,0 (прозрачный), представляющее степень прозрачности штриха. |
| [Visible](../../aspose.words.drawing/stroke/visible/) { get; set; } | Получает или задает флаг, указывающий, виден ли штрих. |
| [Weight](../../aspose.words.drawing/stroke/weight/) { get; set; } | Определяет толщину кисти, которая обводит контур фигуры в пунктах. |

### Примечания

Использовать[`Stroke`](../shape/stroke/)для доступа к свойствам обводки фигуры. Вы не создаете экземпляры`Stroke` класс напрямую.

### Примеры

Показывает, как изменяются свойства обводки.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);

// Базовые фигуры, такие как прямоугольник, имеют две видимые части.
// 1 - Заливка, которая применяется к области внутри контура фигуры:
shape.Fill.ForeColor = Color.White;

// 2 - Обводка, обозначающая контур фигуры:
// Изменяем различные свойства обводки этой фигуры.
Stroke stroke = shape.Stroke;
stroke.On = true;
stroke.Weight = 5;
stroke.Color = Color.Red;
stroke.DashStyle = DashStyle.ShortDashDotDot;
stroke.JoinStyle = JoinStyle.Miter;
stroke.EndCap = EndCap.Square;
stroke.LineStyle = ShapeLineStyle.Triple;

doc.Save(ArtifactsDir + "Shape.Stroke.docx");
```

### Смотрите также

* пространство имен [Aspose.Words.Drawing](../../aspose.words.drawing/)
* сборка [Aspose.Words](../../)


