---
title: Enum AxisTickLabelPosition
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.Charts.AxisTickLabelPosition перечисление. Определяет возможные позиции для галочек.
type: docs
weight: 570
url: /ru/net/aspose.words.drawing.charts/axisticklabelposition/
---
## AxisTickLabelPosition enumeration

Определяет возможные позиции для галочек.

```csharp
public enum AxisTickLabelPosition
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| High | `0` | Указывает, что метки оси должны располагаться на верхнем конце перпендикулярной оси. |
| Low | `1` | Указывает, что метки оси должны располагаться на нижнем конце перпендикулярной оси. |
| NextToAxis | `2` | Указывает, что метки оси должны быть рядом с осью. |
| None | `3` | Указывает, что метки осей не рисуются. |
| Default | `2` | Задает значение по умолчанию для положения галочек. |

### Примеры

Показывает, как вставить диаграмму со значениями даты/времени.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Очистить серию демонстрационных данных диаграммы, чтобы начать с чистой диаграммы.
chart.Series.Clear();

// Добавьте пользовательский ряд, содержащий значения даты/времени для оси X и соответствующие десятичные значения для оси Y.
chart.Series.Add("Aspose Test Series",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });

// Установите нижнюю и верхнюю границы для оси X.
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03));

// Установите основные единицы оси X на неделю, а второстепенные единицы на день.
xAxis.BaseTimeUnit = AxisTimeUnit.Days;
xAxis.MajorUnit = 7.0d;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorUnit = 1.0d;
xAxis.MinorTickMark = AxisTickMark.Outside;

// Определить свойства оси Y для десятичных значений.
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100.0d;
yAxis.MinorUnit = 50.0d;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);

doc.Save(ArtifactsDir + "Charts.DateTimeValues.docx");
```

### Смотрите также

* пространство имен [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* сборка [Aspose.Words](../../)


