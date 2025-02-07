---
title: TextBox.TextBoxWrapMode
second_title: Справочник по API Aspose.Words для .NET
description: TextBox свойство. Определяет как текст обтекает фигуру.
type: docs
weight: 100
url: /ru/net/aspose.words.drawing/textbox/textboxwrapmode/
---
## TextBox.TextBoxWrapMode property

Определяет, как текст обтекает фигуру.

```csharp
public TextBoxWrapMode TextBoxWrapMode { get; set; }
```

### Примечания

Значение по умолчаниюSquare.

### Примеры

Показывает, как установить режим переноса содержимого текстового поля.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 300, 300);
TextBox textBox = textBoxShape.TextBox;

// Установите для свойства "TextBoxWrapMode" значение "TextBoxWrapMode.None", чтобы увеличить ширину текстового поля
// для размещения текста, если он достаточно большой.
// Установите для свойства "TextBoxWrapMode" значение "TextBoxWrapMode.Square", чтобы
// обернуть весь текст внутри текстового поля, сохранив его размеры.
textBox.TextBoxWrapMode = textBoxWrapMode;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Font.Size = 32;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "Shape.TextBoxContentsWrapMode.docx");
```

### Смотрите также

* enum [TextBoxWrapMode](../../textboxwrapmode/)
* class [TextBox](../)
* пространство имен [Aspose.Words.Drawing](../../textbox/)
* сборка [Aspose.Words](../../../)


