---
title: Class ChartDataPoint
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.Charts.ChartDataPoint klas. Ermöglicht die Formatierung eines einzelnen Datenpunkts im Diagramm festzulegen.
type: docs
weight: 650
url: /de/net/aspose.words.drawing.charts/chartdatapoint/
---
## ChartDataPoint class

Ermöglicht die Formatierung eines einzelnen Datenpunkts im Diagramm festzulegen.

```csharp
public class ChartDataPoint : IChartDataPoint
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Bubble3D](../../aspose.words.drawing.charts/chartdatapoint/bubble3d/) { get; set; } |  |
| [Explosion](../../aspose.words.drawing.charts/chartdatapoint/explosion/) { get; set; } |  |
| [Format](../../aspose.words.drawing.charts/chartdatapoint/format/) { get; } | Bietet Zugriff auf die Füll- und Linienformatierung dieses Datenpunkts. |
| [Index](../../aspose.words.drawing.charts/chartdatapoint/index/) { get; } | Index des Datenpunkts, auf den dieses Objekt die Formatierung anwendet. |
| [InvertIfNegative](../../aspose.words.drawing.charts/chartdatapoint/invertifnegative/) { get; set; } |  |
| [Marker](../../aspose.words.drawing.charts/chartdatapoint/marker/) { get; } |  |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [ClearFormat](../../aspose.words.drawing.charts/chartdatapoint/clearformat/)() | Löscht das Format dieses Datenpunkts. Die Eigenschaften werden auf die Standardwerte gesetzt, die in der übergeordneten Serie definiert sind. |

### Bemerkungen

Auf einer Reihe, die`ChartDataPoint` Objekt ist ein Mitglied von[`ChartDataPointCollection`](../chartdatapointcollection/) . Die[`ChartDataPointCollection`](../chartdatapointcollection/) enthält ein`ChartDataPoint` Objekt für jeden Punkt.

### Beispiele

Zeigt, wie Sie mit Datenpunkten in einem Liniendiagramm arbeiten.

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

    // Heben Sie die Datenpunkte des Diagramms hervor, indem Sie sie als Rautenformen erscheinen lassen.
    foreach (ChartSeries series in chart.Series) 
        ApplyDataPoints(series, 4, MarkerSymbol.Diamond, 15);

    // Die Linie glätten, die die erste Datenreihe darstellt.
    chart.Series[0].Smooth = true;

    // Sicherstellen, dass Datenpunkte für die erste Serie ihre Farben nicht invertieren, wenn der Wert negativ ist.
    using (IEnumerator<ChartDataPoint> enumerator = chart.Series[0].DataPoints.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Assert.False(enumerator.Current.InvertIfNegative);
        }
    }

    // Für ein sauberer aussehendes Diagramm können wir das Format individuell löschen.
    chart.Series[1].DataPoints[2].ClearFormat();

    // Wir können auch eine ganze Reihe von Datenpunkten auf einmal entfernen.
    chart.Series[2].DataPoints.ClearFormat();

    doc.Save(ArtifactsDir + "Charts.ChartDataPoint.docx");
}

/// <summary>
/// Wendet eine Reihe von Datenpunkten auf eine Reihe an.
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

### Siehe auch

* interface [IChartDataPoint](../ichartdatapoint/)
* namensraum [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* Montage [Aspose.Words](../../)


