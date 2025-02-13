---
title: Class ChartSeries
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.Charts.ChartSeries сорт. Представляет свойства ряда диаграммы.
type: docs
weight: 730
url: /ru/net/aspose.words.drawing.charts/chartseries/
---
## ChartSeries class

Представляет свойства ряда диаграммы.

```csharp
public class ChartSeries : IChartDataPoint
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Bubble3D](../../aspose.words.drawing.charts/chartseries/bubble3d/) { get; set; } |  |
| [DataLabels](../../aspose.words.drawing.charts/chartseries/datalabels/) { get; } | Задает настройки меток данных для всей серии. |
| [DataPoints](../../aspose.words.drawing.charts/chartseries/datapoints/) { get; } | Возвращает коллекцию объектов форматирования для всех точек данных в этой серии. |
| [Explosion](../../aspose.words.drawing.charts/chartseries/explosion/) { get; set; } |  |
| [Format](../../aspose.words.drawing.charts/chartseries/format/) { get; } | Предоставляет доступ к заполнению и форматированию строк серии. |
| [HasDataLabels](../../aspose.words.drawing.charts/chartseries/hasdatalabels/) { get; set; } | Получает или задает флаг, указывающий, отображаются ли метки данных для ряда. |
| [InvertIfNegative](../../aspose.words.drawing.charts/chartseries/invertifnegative/) { get; set; } |  |
| [LegendEntry](../../aspose.words.drawing.charts/chartseries/legendentry/) { get; } | Получает запись легенды для этой серии диаграмм. |
| [Marker](../../aspose.words.drawing.charts/chartseries/marker/) { get; } |  |
| [Name](../../aspose.words.drawing.charts/chartseries/name/) { get; set; } | Получает или задает имя серии, если имя не задано явно, оно генерируется с использованием индекса. По умолчанию возвращает серию плюс один основанный индекс. |
| [Smooth](../../aspose.words.drawing.charts/chartseries/smooth/) { get; set; } | Позволяет указать, будет ли линия, соединяющая точки на графике, сглаживаться с помощью сплайнов Catmull-Rom. |

### Примеры

Показывает, как применять метки к точкам данных на линейной диаграмме.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    Shape chartShape = builder.InsertChart(ChartType.Line, 400, 300);
    Chart chart = chartShape.Chart;

    Assert.AreEqual(3, chart.Series.Count);
    Assert.AreEqual("Series 1", chart.Series[0].Name);
    Assert.AreEqual("Series 2", chart.Series[1].Name);
    Assert.AreEqual("Series 3", chart.Series[2].Name);

    // Применяем метки данных к каждому ряду на диаграмме.
    // Эти метки будут отображаться рядом с каждой точкой данных на графике и отображать ее значение.
    foreach (ChartSeries series in chart.Series)
    {
        ApplyDataLabels(series, 4, "000.0", ", ");
        Assert.AreEqual(4, series.DataLabels.Count);
    }

    // Изменить строку-разделитель для каждой метки данных в серии.
    using (IEnumerator<ChartDataLabel> enumerator = chart.Series[0].DataLabels.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Assert.AreEqual(", ", enumerator.Current.Separator);
            enumerator.Current.Separator = " & ";
        }
    }

    // Чтобы график выглядел чище, мы можем удалить метки данных по отдельности.
    chart.Series[1].DataLabels[2].ClearFormat();

    // Мы также можем сразу удалить целую серию его меток данных.
    chart.Series[2].DataLabels.ClearFormat();

    doc.Save(ArtifactsDir + "Charts.DataLabels.docx");
}

/// <summary>
/// Применить метки данных с пользовательским числовым форматом и разделителем к нескольким точкам данных в ряду.
/// </summary>
private static void ApplyDataLabels(ChartSeries series, int labelsCount, string numberFormat, string separator)
{
    for (int i = 0; i < labelsCount; i++)
    {
        series.HasDataLabels = true;

        Assert.False(series.DataLabels[i].IsVisible);

        series.DataLabels[i].ShowCategoryName = true;
        series.DataLabels[i].ShowSeriesName = true;
        series.DataLabels[i].ShowValue = true;
        series.DataLabels[i].ShowLeaderLines = true;
        series.DataLabels[i].ShowLegendKey = true;
        series.DataLabels[i].ShowPercentage = false;
        series.DataLabels[i].IsHidden = false;
        Assert.False(series.DataLabels[i].ShowDataLabelsRange);

        series.DataLabels[i].NumberFormat.FormatCode = numberFormat;
        series.DataLabels[i].Separator = separator;

        Assert.False(series.DataLabels[i].ShowDataLabelsRange);
        Assert.True(series.DataLabels[i].IsVisible);
        Assert.False(series.DataLabels[i].IsHidden);
    }
}
```

### Смотрите также

* interface [IChartDataPoint](../ichartdatapoint/)
* пространство имен [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* сборка [Aspose.Words](../../)


