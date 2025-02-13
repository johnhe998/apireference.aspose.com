---
title: ChartDataLabelCollection.ShowLeaderLines
second_title: Справочник по API Aspose.Words для .NET
description: ChartDataLabelCollection свойство. Позволяет указать нужно ли отображать линии выноски меток данных для меток данных всей серии. Значение по умолчанию ЛОЖЬ .
type: docs
weight: 80
url: /ru/net/aspose.words.drawing.charts/chartdatalabelcollection/showleaderlines/
---
## ChartDataLabelCollection.ShowLeaderLines property

Позволяет указать, нужно ли отображать линии выноски меток данных для меток данных всей серии. Значение по умолчанию: **ЛОЖЬ** .

```csharp
public bool ShowLeaderLines { get; set; }
```

### Примечания

Применяется только к круговым диаграммам. Линии выноски создают визуальную связь между меткой данных и соответствующей точкой данных.

Значение, определенное для этого свойства, можно переопределить для отдельной метки данных с помощью параметра the .[`ShowLeaderLines`](../../chartdatalabel/showleaderlines/) имущество.

### Примеры

Показывает, как работать с метками данных круговой диаграммы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Pie, 500, 300).Chart;

// Очистить серию демонстрационных данных диаграммы, чтобы начать с чистой диаграммы.
chart.Series.Clear();

// Вставьте пользовательскую серию диаграмм с названием категории для каждого из секторов и их таблицей частот.
ChartSeries series = chart.Series.Add("Aspose Test Series",
    new[] { "Word", "PDF", "Excel" },
    new[] { 2.7, 3.2, 0.8 });

// Включить метки данных, которые будут отображать как процент, так и частоту каждого сектора, и изменять их внешний вид.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowLeaderLines = true;
dataLabels.ShowLegendKey = true;
dataLabels.ShowPercentage = true;
dataLabels.ShowValue = true;
dataLabels.Separator = "; ";

doc.Save(ArtifactsDir + "Charts.DataLabelsPieChart.docx");
```

### Смотрите также

* class [ChartDataLabelCollection](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* сборка [Aspose.Words](../../../)


