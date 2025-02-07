---
title: Class ChartSeries
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.Charts.ChartSeries klass. Representerar diagramserieegenskaper.
type: docs
weight: 730
url: /sv/net/aspose.words.drawing.charts/chartseries/
---
## ChartSeries class

Representerar diagramserieegenskaper.

```csharp
public class ChartSeries : IChartDataPoint
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Bubble3D](../../aspose.words.drawing.charts/chartseries/bubble3d/) { get; set; } |  |
| [DataLabels](../../aspose.words.drawing.charts/chartseries/datalabels/) { get; } | Anger inställningarna för dataetiketterna för hela serien. |
| [DataPoints](../../aspose.words.drawing.charts/chartseries/datapoints/) { get; } | Returnerar en samling formateringsobjekt för alla datapunkter i denna serie. |
| [Explosion](../../aspose.words.drawing.charts/chartseries/explosion/) { get; set; } |  |
| [Format](../../aspose.words.drawing.charts/chartseries/format/) { get; } | Ger tillgång till fyllnings- och radformatering av serien. |
| [HasDataLabels](../../aspose.words.drawing.charts/chartseries/hasdatalabels/) { get; set; } | Hämtar eller ställer in en flagga som indikerar om dataetiketter visas för serien. |
| [InvertIfNegative](../../aspose.words.drawing.charts/chartseries/invertifnegative/) { get; set; } |  |
| [LegendEntry](../../aspose.words.drawing.charts/chartseries/legendentry/) { get; } | Får en legendpost för denna diagramserie. |
| [Marker](../../aspose.words.drawing.charts/chartseries/marker/) { get; } |  |
| [Name](../../aspose.words.drawing.charts/chartseries/name/) { get; set; } | Hämtar eller ställer in namnet på serien, om namnet inte anges explicit genereras det med index. Som standard returnerar Series plus ett baserat index. |
| [Smooth](../../aspose.words.drawing.charts/chartseries/smooth/) { get; set; } | Gör det möjligt att ange om linjen som förbinder punkterna på diagrammet ska jämnas ut med Catmull-Rom splines. |

### Exempel

Visar hur man applicerar etiketter på datapunkter i ett linjediagram.

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

    // Använd dataetiketter på varje serie i diagrammet.
    // Dessa etiketter visas bredvid varje datapunkt i grafen och visar dess värde.
    foreach (ChartSeries series in chart.Series)
    {
        ApplyDataLabels(series, 4, "000.0", ", ");
        Assert.AreEqual(4, series.DataLabels.Count);
    }

    // Ändra separatorsträngen för varje dataetikett i en serie.
    using (IEnumerator<ChartDataLabel> enumerator = chart.Series[0].DataLabels.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Assert.AreEqual(", ", enumerator.Current.Separator);
            enumerator.Current.Separator = " & ";
        }
    }

    // För en renare graf kan vi ta bort dataetiketter individuellt.
    chart.Series[1].DataLabels[2].ClearFormat();

    // Vi kan också ta bort en hel serie av dess dataetiketter på en gång.
    chart.Series[2].DataLabels.ClearFormat();

    doc.Save(ArtifactsDir + "Charts.DataLabels.docx");
}

/// <summary>
/// Använd dataetiketter med anpassat nummerformat och separator på flera datapunkter i en serie.
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

### Se även

* interface [IChartDataPoint](../ichartdatapoint/)
* namnutrymme [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* hopsättning [Aspose.Words](../../)


