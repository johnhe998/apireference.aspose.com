---
title: ShapeBase.GetShapeRenderer
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase метод. Создает и возвращает объект который можно использовать для преобразования этой формы в изображение.
type: docs
weight: 600
url: /ru/net/aspose.words.drawing/shapebase/getshaperenderer/
---
## ShapeBase.GetShapeRenderer method

Создает и возвращает объект, который можно использовать для преобразования этой формы в изображение.

```csharp
public ShapeRenderer GetShapeRenderer()
```

### Возвращаемое значение

Объект визуализации для этой формы.

### Примечания

Этот метод просто вызывает[`ShapeRenderer`](../../../aspose.words.rendering/shaperenderer/) конструктор и передает этот объект в качестве параметра.

### Примеры

Показывает, как использовать средство визуализации фигур для экспорта фигур в файлы в локальной файловой системе.

```csharp
Document doc = new Document(MyDir + "Various shapes.docx");
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(7, shapes.Length);

// В документе 7 фигур, в том числе одна групповая фигура с 2 дочерними фигурами.
// Мы будем отображать каждую фигуру в файл изображения в локальной файловой системе
// при игнорировании групповых форм, поскольку они не имеют внешнего вида.
// Это создаст 6 файлов изображений.
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>())
{
    ShapeRenderer renderer = shape.GetShapeRenderer();
    ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
    renderer.Save(ArtifactsDir + $"Shape.RenderAllShapes.{shape.Name}.png", options);
}
```

### Смотрите также

* class [ShapeRenderer](../../../aspose.words.rendering/shaperenderer/)
* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


