---
title: ShapeBase.CanHaveImage
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Возвращает true если тип фигуры позволяет фигуре иметь изображение.
type: docs
weight: 100
url: /ru/net/aspose.words.drawing/shapebase/canhaveimage/
---
## ShapeBase.CanHaveImage property

Возвращает true, если тип фигуры позволяет фигуре иметь изображение.

```csharp
public bool CanHaveImage { get; }
```

### Примечания

Хотя Microsoft Word имеет специальный тип фигуры для изображений, кажется, что в документах Microsoft Word любой shape , кроме групповой фигуры, может иметь изображение, поэтому это свойство возвращает значение true для всех фигур, кроме[`GroupShape`](../../groupshape/).

### Примеры

Показывает, как вставить и повернуть изображение.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставляем фигуру с изображением.
Shape shape = builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
Assert.True(shape.CanHaveImage);
Assert.True(shape.HasImage);

// Поворот изображения на 45 градусов по часовой стрелке.
shape.Rotation = 45;

doc.Save(ArtifactsDir + "Shape.Rotate.docx");
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


