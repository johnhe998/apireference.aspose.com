---
title: HorizontalRuleFormat.WidthPercent
second_title: Справочник по API Aspose.Words для .NET
description: HorizontalRuleFormat свойство. Получает или задает длину указанной горизонтальной линейки выраженную в процентах от ширины окна.
type: docs
weight: 50
url: /ru/net/aspose.words.drawing/horizontalruleformat/widthpercent/
---
## HorizontalRuleFormat.WidthPercent property

Получает или задает длину указанной горизонтальной линейки, выраженную в процентах от ширины окна.

```csharp
public double WidthPercent { get; set; }
```

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentOutOfRangeException | Выдает, когда аргумент находится вне диапазона допустимых значений. |

### Примечания

Допустимые значения находятся в диапазоне от 1 до 100 включительно.

Значение по умолчанию — 100.

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


