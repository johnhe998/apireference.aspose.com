---
title: Font.Name
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Получает или задает имя шрифта.
type: docs
weight: 230
url: /ru/net/aspose.words/font/name/
---
## Font.Name property

Получает или задает имя шрифта.

```csharp
public string Name { get; set; }
```

### Примечания

При получении возвращает[`NameAscii`](../nameascii/).

При настройке устанавливает[`NameAscii`](../nameascii/) ,[`NameBi`](../namebi/) ,[`NameFarEast`](../namefareast/) и[`NameOther`](../nameother/) к указанному значению.

### Примеры

Показывает, как отформатировать набор текста, используя его свойство шрифта.

```csharp
Document doc = new Document();
Run run = new Run(doc, "Hello world!");

Aspose.Words.Font font = run.Font;
font.Name = "Courier New";
font.Size = 36;
font.HighlightColor = Color.Yellow;

doc.FirstSection.Body.FirstParagraph.AppendChild(run);
doc.Save(ArtifactsDir + "Font.CreateFormattedRun.docx");
```

Показывает, как вставлять форматированный текст с помощью DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Задайте форматирование шрифта, затем добавьте текст.
Aspose.Words.Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Courier New";
font.Underline = Underline.Dash;

builder.Write("Hello world!");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


