---
title: ShapeBase.IsTopLevel
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Возвращает true если эта фигура не является дочерней фигурой группы.
type: docs
weight: 340
url: /ru/net/aspose.words.drawing/shapebase/istoplevel/
---
## ShapeBase.IsTopLevel property

Возвращает true, если эта фигура не является дочерней фигурой группы.

```csharp
public bool IsTopLevel { get; }
```

### Примеры

Показывает, как определить, является ли фигура частью групповой фигуры.

```csharp
Document doc = new Document();

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
shape.WrapType = WrapType.None;

// Фигура по умолчанию не является частью какой-либо групповой фигуры, поэтому свойство «IsTopLevel» имеет значение «true».
Assert.True(shape.IsTopLevel);

GroupShape group = new GroupShape(doc);
group.AppendChild(shape);

// Как только мы ассимилируем фигуру в групповую, свойство «IsTopLevel» изменится на «false».
Assert.False(shape.IsTopLevel);
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


