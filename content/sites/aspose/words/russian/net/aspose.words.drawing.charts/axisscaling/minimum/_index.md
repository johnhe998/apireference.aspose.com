---
title: AxisScaling.Minimum
second_title: Справочник по API Aspose.Words для .NET
description: AxisScaling свойство. Получает или устанавливает минимальное значение оси.
type: docs
weight: 40
url: /ru/net/aspose.words.drawing.charts/axisscaling/minimum/
---
## AxisScaling.Minimum property

Получает или устанавливает минимальное значение оси.

```csharp
public AxisBound Minimum { get; set; }
```

### Примечания

Значение по умолчанию — "авто".

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

* class [AxisBound](../../axisbound/)
* class [AxisScaling](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../axisscaling/)
* сборка [Aspose.Words](../../../)


