---
title: ChartDataPoint.Format
second_title: Aspose.Words für .NET-API-Referenz
description: ChartDataPoint eigendom. Bietet Zugriff auf die Füll und Linienformatierung dieses Datenpunkts.
type: docs
weight: 30
url: /de/net/aspose.words.drawing.charts/chartdatapoint/format/
---
## ChartDataPoint.Format property

Bietet Zugriff auf die Füll- und Linienformatierung dieses Datenpunkts.

```csharp
public ChartFormat Format { get; }
```

### Beispiele

Zeigt, wie Sie individuelle Formatierungen für Kategorien eines Säulendiagramms festlegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;

// Standardmäßig generierte Serie löschen.
chart.Series.Clear();

// Neue Serie hinzufügen.
ChartSeries series = chart.Series.Add("Series 1",
    new[] { "Category 1", "Category 2", "Category 3", "Category 4" },
    new double[] { 1, 2, 3, 4 });

// Spaltenformatierung festlegen.
ChartDataPointCollection dataPoints = series.DataPoints;
dataPoints[0].Format.Fill.PresetTextured(PresetTexture.Denim);
dataPoints[1].Format.Fill.ForeColor = Color.Red;
dataPoints[2].Format.Fill.ForeColor = Color.Yellow;
dataPoints[3].Format.Fill.ForeColor = Color.Blue;

doc.Save(ArtifactsDir + "Charts.DataPointsFormatting.docx");
```

### Siehe auch

* class [ChartFormat](../../chartformat/)
* class [ChartDataPoint](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartdatapoint/)
* Montage [Aspose.Words](../../../)


