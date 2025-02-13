---
title: TextBox.VerticalAnchor
second_title: Справочник по API Aspose.Words для .NET
description: TextBox свойство. Задает вертикальное выравнивание текста внутри фигуры.
type: docs
weight: 110
url: /ru/net/aspose.words.drawing/textbox/verticalanchor/
---
## TextBox.VerticalAnchor property

Задает вертикальное выравнивание текста внутри фигуры.

```csharp
public TextBoxAnchor VerticalAnchor { get; set; }
```

### Примечания

Значение по умолчаниюTop.

### Примеры

Показывает, как вертикально выровнять текстовое содержимое текстового поля.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.TextBox, 200, 200);

// Установите для свойства "VerticalAnchor" значение "TextBoxAnchor.Top", чтобы
// выровняйте текст в этом текстовом поле по верхней стороне фигуры.
// Установите для свойства "VerticalAnchor" значение "TextBoxAnchor.Middle", чтобы
// выравниваем текст в этом текстовом поле по центру фигуры.
// Установите для свойства "VerticalAnchor" значение "TextBoxAnchor.Bottom", чтобы
// выравниваем текст в этом текстовом поле по нижней части фигуры.
shape.TextBox.VerticalAnchor = verticalAnchor;

builder.MoveTo(shape.FirstParagraph);
builder.Write("Hello world!");

// Вертикальное выравнивание текста внутри текстовых полей доступно, начиная с Microsoft Word 2007.
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2007);
doc.Save(ArtifactsDir + "Shape.VerticalAnchor.docx");
```

### Смотрите также

* enum [TextBoxAnchor](../../textboxanchor/)
* class [TextBox](../)
* пространство имен [Aspose.Words.Drawing](../../textbox/)
* сборка [Aspose.Words](../../../)


