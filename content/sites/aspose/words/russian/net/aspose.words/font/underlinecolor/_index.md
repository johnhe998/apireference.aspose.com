---
title: Font.UnderlineColor
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Получает или задает цвет подчеркивания шрифта.
type: docs
weight: 540
url: /ru/net/aspose.words/font/underlinecolor/
---
## Font.UnderlineColor property

Получает или задает цвет подчеркивания шрифта.

```csharp
public Color UnderlineColor { get; set; }
```

### Примеры

Показывает, как настроить стиль и цвет подчеркивания текста.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Underline = Underline.Dotted;
builder.Font.UnderlineColor = Color.Red;

builder.Writeln("Underlined text.");

doc.Save(ArtifactsDir + "Font.Underlines.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


