---
title: ParagraphFormat.KeepTogether
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Истинно если все строки абзаца должны оставаться на одной странице.
type: docs
weight: 150
url: /ru/net/aspose.words/paragraphformat/keeptogether/
---
## ParagraphFormat.KeepTogether property

Истинно, если все строки абзаца должны оставаться на одной странице.

```csharp
public bool KeepTogether { get; set; }
```

### Примеры

Показывает, как вставить абзац в документ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;
paragraphFormat.KeepTogether = true;

// Метод Writeln завершает абзац после добавления текста
// и затем начинает новую строку, добавляя новый абзац.
builder.Writeln("Hello world!");

Assert.True(builder.CurrentParagraph.IsEndOfDocument);
```

### Смотрите также

* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


