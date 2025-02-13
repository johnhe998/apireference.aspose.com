---
title: HorizontalRuleFormat.Color
second_title: Справочник по API Aspose.Words для .NET
description: HorizontalRuleFormat свойство. Получает или задает цвет кисти заполняющий горизонтальную линейку.
type: docs
weight: 20
url: /ru/net/aspose.words.drawing/horizontalruleformat/color/
---
## HorizontalRuleFormat.Color property

Получает или задает цвет кисти, заполняющий горизонтальную линейку.

```csharp
public Color Color { get; set; }
```

### Примечания

Это ярлык дляColor имущество.

Значение по умолчанию: Gray.

### Примеры

Показывает, как вставить фигуру горизонтальной линейки и настроить ее форматирование.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

Assert.True(shape.IsHorizontalRule);
Assert.True(shape.HorizontalRuleFormat.NoShade);
```

### Смотрите также

* class [HorizontalRuleFormat](../)
* пространство имен [Aspose.Words.Drawing](../../horizontalruleformat/)
* сборка [Aspose.Words](../../../)


