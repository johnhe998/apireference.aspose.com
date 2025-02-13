---
title: Stroke.LineStyle
second_title: Справочник по API Aspose.Words для .NET
description: Stroke свойство. Определяет стиль линии штриха.
type: docs
weight: 120
url: /ru/net/aspose.words.drawing/stroke/linestyle/
---
## Stroke.LineStyle property

Определяет стиль линии штриха.

```csharp
public ShapeLineStyle LineStyle { get; set; }
```

### Примечания

Значение по умолчаниюSingle.

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

* enum [ShapeLineStyle](../../shapelinestyle/)
* class [Stroke](../)
* пространство имен [Aspose.Words.Drawing](../../stroke/)
* сборка [Aspose.Words](../../../)


