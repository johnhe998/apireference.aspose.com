---
title: Stroke.Color2
second_title: Справочник по API Aspose.Words для .NET
description: Stroke свойство. Определяет второй цвет обводки.
type: docs
weight: 30
url: /ru/net/aspose.words.drawing/stroke/color2/
---
## Stroke.Color2 property

Определяет второй цвет обводки.

```csharp
public Color Color2 { get; set; }
```

### Примечания

Значение по умолчанию для[`Shape`](../../shape/)White.

### Примеры

Показывает, как обрабатывать элементы обводки формы.

```csharp
Document doc = new Document(MyDir + "Shape stroke pattern border.docx");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
Stroke stroke = shape.Stroke;

// Штрихи могут иметь два цвета, которые используются для создания шаблона, определяемого данными двухцветного изображения.
// Обводки одного цвета не используют свойство Color2.
Assert.AreEqual(Color.FromArgb(255, 128, 0, 0), stroke.Color);
Assert.AreEqual(Color.FromArgb(255, 255, 255, 0), stroke.Color2);

Assert.NotNull(stroke.ImageBytes);
File.WriteAllBytes(ArtifactsDir + "Drawing.StrokePattern.png", stroke.ImageBytes);
```

### Смотрите также

* class [Stroke](../)
* пространство имен [Aspose.Words.Drawing](../../stroke/)
* сборка [Aspose.Words](../../../)


