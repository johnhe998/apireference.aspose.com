---
title: Class ChartDataPoint
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.Charts.ChartDataPoint clase. Permite especificar el formato de un solo punto de datos en el gráfico.
type: docs
weight: 650
url: /es/net/aspose.words.drawing.charts/chartdatapoint/
---
## ChartDataPoint class

Permite especificar el formato de un solo punto de datos en el gráfico.

```csharp
public class ChartDataPoint : IChartDataPoint
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Bubble3D](../../aspose.words.drawing.charts/chartdatapoint/bubble3d/) { get; set; } |  |
| [Explosion](../../aspose.words.drawing.charts/chartdatapoint/explosion/) { get; set; } |  |
| [Format](../../aspose.words.drawing.charts/chartdatapoint/format/) { get; } | Proporciona acceso al formato de relleno y línea de este punto de datos. |
| [Index](../../aspose.words.drawing.charts/chartdatapoint/index/) { get; } | Índice del punto de datos al que este objeto aplica formato. |
| [InvertIfNegative](../../aspose.words.drawing.charts/chartdatapoint/invertifnegative/) { get; set; } |  |
| [Marker](../../aspose.words.drawing.charts/chartdatapoint/marker/) { get; } |  |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [ClearFormat](../../aspose.words.drawing.charts/chartdatapoint/clearformat/)() | Borra el formato de este punto de datos. Las propiedades se establecen en los valores predeterminados definidos en la serie principal. |

### Observaciones

En una serie, el`ChartDataPoint` objeto es un miembro de la[`ChartDataPointCollection`](../chartdatapointcollection/) . El[`ChartDataPointCollection`](../chartdatapointcollection/) contiene una`ChartDataPoint` objeto para cada punto.

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

* interface [IChartDataPoint](../ichartdatapoint/)
* espacio de nombres [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* asamblea [Aspose.Words](../../)


