---
title: ConvertUtil.PointToInch
second_title: Справочник по API Aspose.Words для .NET
description: ConvertUtil метод. Преобразует пункты в дюймы.
type: docs
weight: 50
url: /ru/net/aspose.words/convertutil/pointtoinch/
---
## ConvertUtil.PointToInch method

Преобразует пункты в дюймы.

```csharp
public static double PointToInch(double points)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| points | Double | Значение для преобразования. |

### Примечания

1 дюйм равен 72 точкам.

### Примеры

Показывает, как указать свойства страницы в дюймах.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Параметр «Параметры страницы» раздела определяет размер полей страницы в пунктах.
// Мы также можем использовать класс «ConvertUtil», чтобы использовать более привычную единицу измерения,
// например дюймы при определении границ.
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(2.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(2.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);

// Дюйм равен 72 точкам.
Assert.AreEqual(72.0d, ConvertUtil.InchToPoint(1));
Assert.AreEqual(1.0d, ConvertUtil.PointToInch(72));

// Добавьте содержимое, чтобы продемонстрировать новые поля.
builder.Writeln($"This Text is {pageSetup.LeftMargin} points/{ConvertUtil.PointToInch(pageSetup.LeftMargin)} inches from the left, " +
                $"{pageSetup.RightMargin} points/{ConvertUtil.PointToInch(pageSetup.RightMargin)} inches from the right, " +
                $"{pageSetup.TopMargin} points/{ConvertUtil.PointToInch(pageSetup.TopMargin)} inches from the top, " +
                $"and {pageSetup.BottomMargin} points/{ConvertUtil.PointToInch(pageSetup.BottomMargin)} inches from the bottom of the page.");

doc.Save(ArtifactsDir + "UtilityClasses.PointsAndInches.docx");
```

### Смотрите также

* class [ConvertUtil](../)
* пространство имен [Aspose.Words](../../convertutil/)
* сборка [Aspose.Words](../../../)


