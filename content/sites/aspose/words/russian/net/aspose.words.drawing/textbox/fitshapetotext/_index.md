---
title: TextBox.FitShapeToText
second_title: Справочник по API Aspose.Words для .NET
description: TextBox свойство. Определяет будет ли Microsoft Word увеличивать фигуру до размера текста.
type: docs
weight: 10
url: /ru/net/aspose.words.drawing/textbox/fitshapetotext/
---
## TextBox.FitShapeToText property

Определяет, будет ли Microsoft Word увеличивать фигуру до размера текста.

```csharp
public bool FitShapeToText { get; set; }
```

### Примечания

Значение по умолчанию **ЛОЖЬ**.

### Примеры

Показывает, как заставить текстовое поле изменить свой размер, чтобы точно соответствовать его содержимому.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Применяем эти значения к обоим элементам, чтобы подогнать родительскую фигуру
// тесно вокруг текстового содержимого, игнорируя установленные нами размеры.
textBox.FitShapeToText = true;
textBox.TextBoxWrapMode = TextBoxWrapMode.None;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text fit tightly inside textbox.");

doc.Save(ArtifactsDir + "Shape.TextBoxFitShapeToText.docx");
```

### Смотрите также

* class [TextBox](../)
* пространство имен [Aspose.Words.Drawing](../../textbox/)
* сборка [Aspose.Words](../../../)


