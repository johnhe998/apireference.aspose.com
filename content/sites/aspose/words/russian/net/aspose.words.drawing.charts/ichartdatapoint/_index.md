---
title: Interface IChartDataPoint
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.Charts.IChartDataPoint интерфейс. Содержит свойства одной точки данных на диаграмме.
type: docs
weight: 770
url: /ru/net/aspose.words.drawing.charts/ichartdatapoint/
---
## IChartDataPoint interface

Содержит свойства одной точки данных на диаграмме.

```csharp
public interface IChartDataPoint
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Bubble3D](../../aspose.words.drawing.charts/ichartdatapoint/bubble3d/) { get; set; } | Указывает, следует ли применять к пузырькам в пузырьковой диаграмме трехмерный эффект. |
| [Explosion](../../aspose.words.drawing.charts/ichartdatapoint/explosion/) { get; set; } | Определяет величину, на которую точка данных должна быть перемещена от центра круговой диаграммы. Может быть отрицательным, отрицательное значение означает, что свойство не установлено и разнесение не должно применяться. Применяется только к круговым диаграммам. |
| [InvertIfNegative](../../aspose.words.drawing.charts/ichartdatapoint/invertifnegative/) { get; set; } | Указывает, должен ли родительский элемент инвертировать свои цвета, если значение отрицательное. |
| [Marker](../../aspose.words.drawing.charts/ichartdatapoint/marker/) { get; } | Указывает маркер данных. Маркер создается автоматически по запросу. |

### Примеры

Показывает, как работать с точками данных на линейной диаграмме.

```csharp
[Test]
public void ChartDataPoint()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    Shape shape = builder.InsertChart(ChartType.Line, 500, 350);
    Chart chart = shape.Chart;

    Assert.AreEqual(3, chart.Series.Count);
    Assert.AreEqual("Series 1", chart.Series[0].Name);
    Assert.AreEqual("Series 2", chart.Series[1].Name);
    Assert.AreEqual("Series 3", chart.Series[2].Name);

    // Подчеркните точки данных диаграммы, сделав их ромбовидными.
    foreach (ChartSeries series in chart.Series) 
        ApplyDataPoints(series, 4, MarkerSymbol.Diamond, 15);

    // Сглаживаем линию, представляющую первый ряд данных.
    chart.Series[0].Smooth = true;

    // Убедитесь, что точки данных для первого ряда не инвертируют свои цвета, если значение отрицательное.
    using (IEnumerator<ChartDataPoint> enumerator = chart.Series[0].DataPoints.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Assert.False(enumerator.Current.InvertIfNegative);
        }
    }

    // Чтобы график выглядел чище, мы можем очистить формат по отдельности.
    chart.Series[1].DataPoints[2].ClearFormat();

    // Мы также можем сразу удалить всю серию точек данных.
    chart.Series[2].DataPoints.ClearFormat();

    doc.Save(ArtifactsDir + "Charts.ChartDataPoint.docx");
}

/// <summary>
/// Применяет ряд точек данных к ряду.
/// </summary>
private static void ApplyDataPoints(ChartSeries series, int dataPointsCount, MarkerSymbol markerSymbol, int dataPointSize)
{
    for (int i = 0; i < dataPointsCount; i++)
    {
        ChartDataPoint point = series.DataPoints[i];
        point.Marker.Symbol = markerSymbol;
        point.Marker.Size = dataPointSize;

        Assert.AreEqual(i, point.Index);
    }
}
```

### Смотрите также

* пространство имен [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* сборка [Aspose.Words](../../)


