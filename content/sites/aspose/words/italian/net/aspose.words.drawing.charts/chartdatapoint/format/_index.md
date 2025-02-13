---
title: ChartDataPoint.Format
second_title: Aspose.Words per .NET API Reference
description: ChartDataPoint proprietà. Fornisce laccesso al riempimento e alla formattazione della linea di questo punto dati.
type: docs
weight: 30
url: /it/net/aspose.words.drawing.charts/chartdatapoint/format/
---
## ChartDataPoint.Format property

Fornisce l'accesso al riempimento e alla formattazione della linea di questo punto dati.

```csharp
public ChartFormat Format { get; }
```

### Esempi

Mostra come impostare la formattazione individuale per le categorie di un istogramma.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;

// Elimina le serie generate di default.
chart.Series.Clear();

// Aggiunta di nuove serie.
ChartSeries series = chart.Series.Add("Series 1",
    new[] { "Category 1", "Category 2", "Category 3", "Category 4" },
    new double[] { 1, 2, 3, 4 });

// Imposta la formattazione delle colonne.
ChartDataPointCollection dataPoints = series.DataPoints;
dataPoints[0].Format.Fill.PresetTextured(PresetTexture.Denim);
dataPoints[1].Format.Fill.ForeColor = Color.Red;
dataPoints[2].Format.Fill.ForeColor = Color.Yellow;
dataPoints[3].Format.Fill.ForeColor = Color.Blue;

doc.Save(ArtifactsDir + "Charts.DataPointsFormatting.docx");
```

### Guarda anche

* class [ChartFormat](../../chartformat/)
* class [ChartDataPoint](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartdatapoint/)
* assemblea [Aspose.Words](../../../)


