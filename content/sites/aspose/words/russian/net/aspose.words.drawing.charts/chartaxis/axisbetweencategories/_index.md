---
title: ChartAxis.AxisBetweenCategories
second_title: Справочник по API Aspose.Words для .NET
description: ChartAxis свойство. Получает или задает флаг указывающий пересекает ли ось значений ось категорий между категориями.
type: docs
weight: 10
url: /ru/net/aspose.words.drawing.charts/chartaxis/axisbetweencategories/
---
## ChartAxis.AxisBetweenCategories property

Получает или задает флаг, указывающий, пересекает ли ось значений ось категорий между категориями.

```csharp
public bool AxisBetweenCategories { get; set; }
```

### Примечания

Свойство действует только для осей значений. Он не поддерживается новыми диаграммами MS Office 2016.

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


