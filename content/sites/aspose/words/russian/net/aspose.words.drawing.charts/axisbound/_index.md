---
title: Class AxisBound
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.Charts.AxisBound сорт. Представляет минимальную или максимальную границу значений оси.
type: docs
weight: 500
url: /ru/net/aspose.words.drawing.charts/axisbound/
---
## AxisBound class

Представляет минимальную или максимальную границу значений оси.

```csharp
public sealed class AxisBound
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [AxisBound](axisbound/#constructor)() | Создает новый экземпляр, указывающий, что привязка оси должна определяться автоматически приложением обработки текста . |
| [AxisBound](axisbound/#constructor_2)(DateTime) | Создает привязку оси, представленную как значение даты и времени. |
| [AxisBound](axisbound/#constructor_1)(double) | Создает границу оси, представленную в виде числа. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [IsAuto](../../aspose.words.drawing.charts/axisbound/isauto/) { get; } | Возвращает флаг, указывающий, что привязка оси должна быть определена автоматически. |
| [Value](../../aspose.words.drawing.charts/axisbound/value/) { get; } | Возвращает числовое значение связанной оси. |
| [ValueAsDate](../../aspose.words.drawing.charts/axisbound/valueasdate/) { get; } | Возвращает значение привязки оси, представленное как datetime. |

## Методы

| Имя | Описание |
| --- | --- |
| override [Equals](../../aspose.words.drawing.charts/axisbound/equals/)(object) | Определяет, равен ли указанный объект по значению текущему объекту. |
| override [GetHashCode](../../aspose.words.drawing.charts/axisbound/gethashcode/)() | Служит хэш-функцией для этого типа. |
| override [ToString](../../aspose.words.drawing.charts/axisbound/tostring/)() | Возвращает удобную для пользователя строку, отображающую значение этого объекта. |

### Примечания

Привязка может быть указана как числовое значение, дата-время или специальное значение "auto".

Экземпляры этого класса неизменяемы.

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


