---
title: Shape.TextBox
second_title: Справочник по API Aspose.Words для .NET
description: Shape свойство. Определяет атрибуты определяющие способ отображения текста в фигуре.
type: docs
weight: 220
url: /ru/net/aspose.words.drawing/shape/textbox/
---
## Shape.TextBox property

Определяет атрибуты, определяющие способ отображения текста в фигуре.

```csharp
public TextBox TextBox { get; }
```

### Примеры

Показывает, как установить ориентацию текста внутри текстового поля.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Переместите конструктор документов внутрь TextBox и добавьте текст.
builder.MoveTo(textBoxShape.LastParagraph);
builder.Writeln("Hello world!");
builder.Write("Hello again!");

// Установите свойство "LayoutFlow", чтобы задать ориентацию текстового содержимого этого текстового поля.
textBox.LayoutFlow = layoutFlow;

doc.Save(ArtifactsDir + "Shape.TextBoxLayoutFlow.docx");
```

### Смотрите также

* class [TextBox](../../textbox/)
* class [Shape](../)
* пространство имен [Aspose.Words.Drawing](../../shape/)
* сборка [Aspose.Words](../../../)


