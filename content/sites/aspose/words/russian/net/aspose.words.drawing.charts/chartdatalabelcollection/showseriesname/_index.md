---
title: ChartDataLabelCollection.ShowSeriesName
second_title: Справочник по API Aspose.Words для .NET
description: ChartDataLabelCollection свойство. Возвращает или задает логическое значение указывающее поведение отображения имени ряда для меток данных всего ряда.  Истинныйчтобы показать название серии. ЛОЖЬ прятаться. По умолчанию ЛОЖЬ .
type: docs
weight: 110
url: /ru/net/aspose.words.drawing.charts/chartdatalabelcollection/showseriesname/
---
## ChartDataLabelCollection.ShowSeriesName property

Возвращает или задает логическое значение, указывающее поведение отображения имени ряда для меток данных всего ряда.  **Истинный**чтобы показать название серии. **ЛОЖЬ** прятаться. По умолчанию **ЛОЖЬ** .

```csharp
public bool ShowSeriesName { get; set; }
```

### Примечания

Значение, определенное для этого свойства, может быть переопределено для отдельной метки данных с помощью параметра [`ShowSeriesName`](../../chartdatalabel/showseriesname/) свойство.

### Примеры

Показывает, как работать с метками данных пузырьковой диаграммы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Bubble, 500, 300).Chart;

// Очистить серию демонстрационных данных диаграммы, чтобы начать с чистой диаграммы.
chart.Series.Clear();

 // Добавьте пользовательскую серию с координатами X/Y и диаметром каждого из пузырьков.
ChartSeries series = chart.Series.Add("Aspose Test Series",
    new[] { 2.9, 3.5, 1.1, 4.0, 4.0 },
    new[] { 1.9, 8.5, 2.1, 6.0, 1.5 },
    new[] { 9.0, 4.5, 2.5, 8.0, 5.0 });

// Включите метки данных, а затем измените их внешний вид.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowBubbleSize = true;
dataLabels.ShowCategoryName = true;
dataLabels.ShowSeriesName = true;
dataLabels.Separator = " & ";

doc.Save(ArtifactsDir + "Charts.DataLabelsBubbleChart.docx");
```

### Смотрите также

* class [ChartDataLabelCollection](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* сборка [Aspose.Words](../../../)


