---
title: HorizontalRuleFormat.Height
second_title: Справочник по API Aspose.Words для .NET
description: HorizontalRuleFormat свойство. Получает или задает высоту горизонтальной линейки.
type: docs
weight: 30
url: /ru/net/aspose.words.drawing/horizontalruleformat/height/
---
## HorizontalRuleFormat.Height property

Получает или задает высоту горизонтальной линейки.

```csharp
public double Height { get; set; }
```

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentOutOfRangeException | Выдает, когда аргумент находится вне диапазона допустимых значений. |

### Примечания

Это ярлык для[`Height`](../../shapebase/height/) имущество.

Допустимые значения находятся в диапазоне от 0 до 1584 включительно.

Значение по умолчанию — 1,5.

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


