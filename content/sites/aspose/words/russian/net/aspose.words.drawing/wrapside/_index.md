---
title: Enum WrapSide
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.WrapSide перечисление. Определяет стороны фигуры или изображения вокруг которых обтекает текст.
type: docs
weight: 1240
url: /ru/net/aspose.words.drawing/wrapside/
---
## WrapSide enumeration

Определяет стороны фигуры или изображения, вокруг которых обтекает текст.

```csharp
public enum WrapSide
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Both | `0` | Текст документа обтекает фигуру с обеих сторон. |
| Left | `1` | Текст документа обтекает только левую часть фигуры. Справа от фигуры есть свободная от текста область. |
| Right | `2` | Текст документа обтекает только правую часть фигуры. В левой части фигуры есть свободная от текста область. |
| Largest | `3` | Текст документа обтекает ту сторону фигуры, которая находится дальше всего от полей страницы, оставляя область свободной от текста на другой стороне фигуры. |
| Default | `0` | Значение по умолчанию:Both . |

### Примеры

Показывает, как заменить все фигуры текстового поля фигурами изображения.

```csharp
Document doc = new Document(MyDir + "Textboxes in drawing canvas.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(3, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(1, shapes.Count(s => s.ShapeType == ShapeType.Image));

foreach (Shape shape in shapes)
{
    if (shape.ShapeType == ShapeType.TextBox)
    {
        Shape replacementShape = new Shape(doc, ShapeType.Image);
        replacementShape.ImageData.SetImage(ImageDir + "Logo.jpg");
        replacementShape.Left = shape.Left;
        replacementShape.Top = shape.Top;
        replacementShape.Width = shape.Width;
        replacementShape.Height = shape.Height;
        replacementShape.RelativeHorizontalPosition = shape.RelativeHorizontalPosition;
        replacementShape.RelativeVerticalPosition = shape.RelativeVerticalPosition;
        replacementShape.HorizontalAlignment = shape.HorizontalAlignment;
        replacementShape.VerticalAlignment = shape.VerticalAlignment;
        replacementShape.WrapType = shape.WrapType;
        replacementShape.WrapSide = shape.WrapSide;

        shape.ParentNode.InsertAfter(replacementShape, shape);
        shape.Remove();
    }
}

shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(0, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(4, shapes.Count(s => s.ShapeType == ShapeType.Image));

doc.Save(ArtifactsDir + "Shape.ReplaceTextboxesWithImages.docx");
```

### Смотрите также

* property [WrapSide](../shapebase/wrapside/)
* пространство имен [Aspose.Words.Drawing](../../aspose.words.drawing/)
* сборка [Aspose.Words](../../)


