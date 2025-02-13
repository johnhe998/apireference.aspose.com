---
title: Class TextBox
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.TextBox сорт. Определяет атрибуты определяющие способ отображения текста внутри фигуры.
type: docs
weight: 1170
url: /ru/net/aspose.words.drawing/textbox/
---
## TextBox class

Определяет атрибуты, определяющие способ отображения текста внутри фигуры.

```csharp
public class TextBox
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [FitShapeToText](../../aspose.words.drawing/textbox/fitshapetotext/) { get; set; } | Определяет, будет ли Microsoft Word увеличивать фигуру до размера текста. |
| [InternalMarginBottom](../../aspose.words.drawing/textbox/internalmarginbottom/) { get; set; } | Указывает внутреннее нижнее поле в точках для фигуры. |
| [InternalMarginLeft](../../aspose.words.drawing/textbox/internalmarginleft/) { get; set; } | Указывает внутреннее левое поле в точках для фигуры. |
| [InternalMarginRight](../../aspose.words.drawing/textbox/internalmarginright/) { get; set; } | Указывает внутреннее правое поле в пунктах для фигуры. |
| [InternalMarginTop](../../aspose.words.drawing/textbox/internalmargintop/) { get; set; } | Указывает внутреннее верхнее поле в пунктах для фигуры. |
| [LayoutFlow](../../aspose.words.drawing/textbox/layoutflow/) { get; set; } | Определяет поток текстового макета в фигуре. |
| [Next](../../aspose.words.drawing/textbox/next/) { get; set; } | Возвращает или задает TextBox, представляющий следующий TextBox в последовательности фигур. |
| [Parent](../../aspose.words.drawing/textbox/parent/) { get; } | Получает родительскую фигуру для TextBox. |
| [Previous](../../aspose.words.drawing/textbox/previous/) { get; } | Возвращает TextBox, представляющий предыдущий TextBox в последовательности фигур. |
| [TextBoxWrapMode](../../aspose.words.drawing/textbox/textboxwrapmode/) { get; set; } | Определяет, как текст обтекает фигуру. |
| [VerticalAnchor](../../aspose.words.drawing/textbox/verticalanchor/) { get; set; } | Задает вертикальное выравнивание текста внутри фигуры. |

## Методы

| Имя | Описание |
| --- | --- |
| [BreakForwardLink](../../aspose.words.drawing/textbox/breakforwardlink/)() | Разрывает ссылку на следующее TextBox. |
| [IsValidLinkTarget](../../aspose.words.drawing/textbox/isvalidlinktarget/)(TextBox) | Определяет, может ли это TextBox быть связано с целевым TextBox. |

### Примечания

Использовать[`TextBox`](../shape/textbox/) свойство для доступа к текстовым свойствам формы. Вы не создаете экземпляры`TextBox` класс напрямую.

### Примеры

Показывает, как установить внутренние поля для текстового поля.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставить другое текстовое поле с определенными полями.
Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 100, 100);
TextBox textBox = textBoxShape.TextBox;
textBox.InternalMarginTop = 15;
textBox.InternalMarginBottom = 15;
textBox.InternalMarginLeft = 15;
textBox.InternalMarginRight = 15;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text placed according to textbox margins.");

doc.Save(ArtifactsDir + "Shape.TextBoxMargins.docx");
```

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

* пространство имен [Aspose.Words.Drawing](../../aspose.words.drawing/)
* сборка [Aspose.Words](../../)


