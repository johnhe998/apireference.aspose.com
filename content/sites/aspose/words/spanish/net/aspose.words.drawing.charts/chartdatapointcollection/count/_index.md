---
title: ChartDataPointCollection.Count
second_title: Referencia de API de Aspose.Words para .NET
description: ChartDataPointCollection propiedad. Devuelve el número deChartDataPoint en esta colección.
type: docs
weight: 10
url: /es/net/aspose.words.drawing.charts/chartdatapointcollection/count/
---
## ChartDataPointCollection.Count property

Devuelve el número de[`ChartDataPoint`](../../chartdatapoint/) en esta colección.

```csharp
public int Count { get; }
```

### Ejemplos

Muestra cómo trabajar con puntos de datos en un gráfico de líneas.

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

    // Enfatice los puntos de datos del gráfico haciéndolos aparecer como formas de diamante.
    foreach (ChartSeries series in chart.Series) 
        ApplyDataPoints(series, 4, MarkerSymbol.Diamond, 15);

    // Suavizar la línea que representa la primera serie de datos.
    chart.Series[0].Smooth = true;

    // Verifique que los puntos de datos de la primera serie no inviertan sus colores si el valor es negativo.
    using (IEnumerator<ChartDataPoint> enumerator = chart.Series[0].DataPoints.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Assert.False(enumerator.Current.InvertIfNegative);
        }
    }

    // Para un gráfico de aspecto más limpio, podemos borrar el formato individualmente.
    chart.Series[1].DataPoints[2].ClearFormat();

    // También podemos eliminar una serie completa de puntos de datos a la vez.
    chart.Series[2].DataPoints.ClearFormat();

    doc.Save(ArtifactsDir + "Charts.ChartDataPoint.docx");
}

/// <summary>
/// Aplica un número de puntos de datos a una serie.
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

### Ver también

* class [ChartDataPointCollection](../)
* espacio de nombres [Aspose.Words.Drawing.Charts](../../chartdatapointcollection/)
* asamblea [Aspose.Words](../../../)


