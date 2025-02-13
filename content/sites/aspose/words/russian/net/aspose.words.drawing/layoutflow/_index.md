---
title: Enum LayoutFlow
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.LayoutFlow перечисление. Определяет поток макета текста в текстовом поле.
type: docs
weight: 970
url: /ru/net/aspose.words.drawing/layoutflow/
---
## LayoutFlow enumeration

Определяет поток макета текста в текстовом поле.

```csharp
public enum LayoutFlow
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Horizontal | `0` | Текст отображается горизонтально. |
| TopToBottomIdeographic | `1` | Идеографический текст отображается вертикально. |
| BottomToTop | `2` | Текст отображается вертикально. |
| TopToBottom | `3` | Текст отображается вертикально. |
| HorizontalIdeographic | `4` | Идеографический текст отображается горизонтально. |
| Vertical | `5` | Текст отображается вертикально. |

### Примеры

Показывает, как добавить текст в текстовое поле и изменить его ориентацию.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textbox = new Shape(doc, ShapeType.TextBox)
{
    Width = 100, 
    Height = 100,
    TextBox = { LayoutFlow = LayoutFlow.BottomToTop }
};

textbox.AppendChild(new Paragraph(doc));
builder.InsertNode(textbox);

builder.MoveTo(textbox.FirstParagraph);
builder.Write("This text is flipped 90 degrees to the left.");

doc.Save(ArtifactsDir + "Drawing.TextBox.docx");
```

### Смотрите также

* property [LayoutFlow](../textbox/layoutflow/)
* пространство имен [Aspose.Words.Drawing](../../aspose.words.drawing/)
* сборка [Aspose.Words](../../)


