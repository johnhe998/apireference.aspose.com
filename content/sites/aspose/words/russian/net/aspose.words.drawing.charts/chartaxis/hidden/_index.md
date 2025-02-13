---
title: ChartAxis.Hidden
second_title: Справочник по API Aspose.Words для .NET
description: ChartAxis свойство. Получает или устанавливает флаг указывающий скрыта эта ось или нет.
type: docs
weight: 80
url: /ru/net/aspose.words.drawing.charts/chartaxis/hidden/
---
## ChartAxis.Hidden property

Получает или устанавливает флаг, указывающий, скрыта эта ось или нет.

```csharp
public bool Hidden { get; set; }
```

### Примечания

Значение по умолчанию: **ЛОЖЬ** .

### Примеры

Показывает, как скрыть оси диаграммы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Очистить серию демонстрационных данных диаграммы, чтобы начать с чистой диаграммы.
chart.Series.Clear();

// Добавьте пользовательский ряд с категориями для оси X и соответствующими десятичными значениями для оси Y.
chart.Series.Add("AW Series 1",
    new[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2 });

 // Скрываем оси графика, чтобы упростить внешний вид графика.
chart.AxisX.Hidden = true;
chart.AxisY.Hidden = true;

doc.Save(ArtifactsDir + "Charts.HideChartAxis.docx");
```

### Смотрите также

* class [ChartAxis](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chartaxis/)
* сборка [Aspose.Words](../../../)


