---
title: ChartAxis.MajorUnitScale
second_title: Справочник по API Aspose.Words для .NET
description: ChartAxis свойство. Возвращает или задает значение шкалы для основных делений на оси категорий времени.
type: docs
weight: 120
url: /ru/net/aspose.words.drawing.charts/chartaxis/majorunitscale/
---
## ChartAxis.MajorUnitScale property

Возвращает или задает значение шкалы для основных делений на оси категорий времени.

```csharp
public AxisTimeUnit MajorUnitScale { get; set; }
```

### Примечания

Свойство действует только для осей категорий времени.

### Примеры

Показывает, как управлять делениями и отображаемыми значениями оси диаграммы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);

// Установите второстепенные деления оси Y так, чтобы они указывали в сторону от области графика,
// и основные деления для пересечения оси.
ChartAxis axis = chart.AxisY;
axis.MajorTickMark = AxisTickMark.Cross;
axis.MinorTickMark = AxisTickMark.Outside;

// Установите ось Y, чтобы показать основной тик каждые 10 единиц и второстепенный тик каждые 1 единицу.
axis.MajorUnit = 10;
axis.MinorUnit = 1;

// Установите границы оси Y на -10 и 20.
// Эта ось Y теперь будет отображать 4 основных деления и 27 второстепенных делений.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(20);

// Для оси X установите основные деления через каждые 10 единиц,
// каждая второстепенная отметка на 2,5 единицы.
axis = chart.AxisX;
axis.MajorUnit = 10;
axis.MinorUnit = 2.5;

// Настройте оба типа делений, чтобы они отображались внутри области построения графика.
axis.MajorTickMark = AxisTickMark.Inside;
axis.MinorTickMark = AxisTickMark.Inside;

// Установите границы по оси X так, чтобы ось X охватывала 5 основных делений и 12 второстепенных делений.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(30);
axis.TickLabelAlignment = ParagraphAlignment.Right;

Assert.AreEqual(1, axis.TickLabelSpacing);

// Установите метки тиков, чтобы отображать их значение в миллионах.
axis.DisplayUnit.Unit = AxisBuiltInUnit.Millions;

// Мы можем установить более конкретное значение, по которому метки тиков будут отображать свои значения.
// Этот оператор эквивалентен приведенному выше.
axis.DisplayUnit.CustomUnit = 1000000;
doc.Save(ArtifactsDir + "Charts.AxisDisplayUnit.docx");
```

### Смотрите также

* enum [AxisTimeUnit](../../axistimeunit/)
* class [ChartAxis](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chartaxis/)
* сборка [Aspose.Words](../../../)


