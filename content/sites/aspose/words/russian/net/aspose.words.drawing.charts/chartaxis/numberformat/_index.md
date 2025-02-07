---
title: ChartAxis.NumberFormat
second_title: Справочник по API Aspose.Words для .NET
description: ChartAxis свойство. ВозвращаетChartNumberFormat объект который позволяет определять числовые форматы для оси.
type: docs
weight: 170
url: /ru/net/aspose.words.drawing.charts/chartaxis/numberformat/
---
## ChartAxis.NumberFormat property

Возвращает[`ChartNumberFormat`](../../chartnumberformat/) объект, который позволяет определять числовые форматы для оси.

```csharp
public ChartNumberFormat NumberFormat { get; }
```

### Примеры

Показывает, как задать форматирование значений диаграммы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// Очистить серию демонстрационных данных диаграммы, чтобы начать с чистой диаграммы.
chart.Series.Clear();

// Добавляем на диаграмму пользовательский ряд с категориями по оси X,
 // и большие соответствующие числовые значения для оси Y.
chart.Series.Add("Aspose Test Series",
    new [] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });

 // Установите числовой формат меток деления оси Y, чтобы не группировать цифры запятыми.
chart.AxisY.NumberFormat.FormatCode = "#,##0";

// Этот флаг может переопределить указанное выше значение и вывести числовой формат из исходной ячейки.
Assert.False(chart.AxisY.NumberFormat.IsLinkedToSource);

doc.Save(ArtifactsDir + "Charts.SetNumberFormatToChartAxis.docx");
```

### Смотрите также

* class [ChartNumberFormat](../../chartnumberformat/)
* class [ChartAxis](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chartaxis/)
* сборка [Aspose.Words](../../../)


