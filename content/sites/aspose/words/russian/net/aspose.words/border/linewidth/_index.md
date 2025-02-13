---
title: Border.LineWidth
second_title: Справочник по API Aspose.Words для .NET
description: Border свойство. Получает или задает ширину границы в пунктах.
type: docs
weight: 50
url: /ru/net/aspose.words/border/linewidth/
---
## Border.LineWidth property

Получает или задает ширину границы в пунктах.

```csharp
public double LineWidth { get; set; }
```

### Примечания

Если вы установите толщину линии больше нуля, когда стиль линии отсутствует, стиль линии is автоматически изменится на одну линию.

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


