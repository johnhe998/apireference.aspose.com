---
title: Border.Color
second_title: Справочник по API Aspose.Words для .NET
description: Border свойство. Получает или задает цвет границы.
type: docs
weight: 10
url: /ru/net/aspose.words/border/color/
---
## Border.Color property

Получает или задает цвет границы.

```csharp
public Color Color { get; set; }
```

### Примеры

Показывает, как вставить в документ строку, окруженную рамкой.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

### Смотрите также

* class [Border](../)
* пространство имен [Aspose.Words](../../border/)
* сборка [Aspose.Words](../../../)


