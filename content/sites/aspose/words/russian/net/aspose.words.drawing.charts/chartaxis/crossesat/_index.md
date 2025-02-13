---
title: ChartAxis.CrossesAt
second_title: Справочник по API Aspose.Words для .NET
description: ChartAxis свойство. Указывает место пересечения оси на перпендикулярной оси.
type: docs
weight: 50
url: /ru/net/aspose.words.drawing.charts/chartaxis/crossesat/
---
## ChartAxis.CrossesAt property

Указывает место пересечения оси на перпендикулярной оси.

```csharp
public double CrossesAt { get; set; }
```

### Примечания

Свойство имеет силу, только если[`Crosses`](../crosses/) настроены наCustom. Не поддерживается новыми диаграммами MS Office 2016.

Единицы определяются типом оси. Когда ось является осью значений, значение property представляет собой десятичное число на оси значений. Если ось представляет собой ось категории времени, значение определяется как целое число дней относительно базовой даты (30/12/1899). Для оси текстовых категорий значение равно целочисленному номеру категории, начиная с 1 в качестве первой категории.

### Примеры

Показывает, как заставить ось графика пересекаться в заданном месте.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// Для столбчатых диаграмм ось Y по умолчанию пересекает ноль,
// это означает, что столбцы для всех значений ниже нуля указывают вниз для представления отрицательных значений.
// Мы можем установить другое значение для пересечения оси Y. В этом случае мы установим его на 3.
ChartAxis axis = chart.AxisX;
axis.Crosses = AxisCrosses.Custom;
axis.CrossesAt = 3;
axis.AxisBetweenCategories = true;

doc.Save(ArtifactsDir + "Charts.AxisCross.docx");
```

### Смотрите также

* class [ChartAxis](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chartaxis/)
* сборка [Aspose.Words](../../../)


