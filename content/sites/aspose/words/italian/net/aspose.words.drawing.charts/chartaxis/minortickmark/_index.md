---
title: ChartAxis.MinorTickMark
second_title: Aspose.Words per .NET API Reference
description: ChartAxis proprietà. Restituisce o imposta i segni di graduazione minori per lasse.
type: docs
weight: 130
url: /it/net/aspose.words.drawing.charts/chartaxis/minortickmark/
---
## ChartAxis.MinorTickMark property

Restituisce o imposta i segni di graduazione minori per l'asse.

```csharp
public AxisTickMark MinorTickMark { get; set; }
```

### Esempi

Mostra come inserire un grafico e modificare l'aspetto dei suoi assi.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// Cancella la serie di dati demo del grafico per iniziare con un grafico pulito.
chart.Series.Clear();

// Inserisce una serie di grafici con categorie per l'asse X e rispettivi valori numerici per l'asse Y.
chart.Series.Add("Aspose Test Series",
    new[] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 640, 320, 280, 120, 150 });

// Gli assi del grafico hanno varie opzioni che possono cambiarne l'aspetto,
// come la direzione, i tick delle unità maggiori/minori e i segni di graduazione.
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Minimum;
xAxis.ReverseOrder = false;
xAxis.MajorTickMark = AxisTickMark.Inside;
xAxis.MinorTickMark = AxisTickMark.Cross;
xAxis.MajorUnit = 10.0d;
xAxis.MinorUnit = 15.0d;
xAxis.TickLabelOffset = 50;
xAxis.TickLabelPosition = AxisTickLabelPosition.Low;
xAxis.TickLabelSpacingIsAuto = false;
xAxis.TickMarkSpacing = 1;

ChartAxis yAxis = chart.AxisY;
yAxis.CategoryType = AxisCategoryType.Automatic;
yAxis.Crosses = AxisCrosses.Maximum;
yAxis.ReverseOrder = true;
yAxis.MajorTickMark = AxisTickMark.Inside;
yAxis.MinorTickMark = AxisTickMark.Cross;
yAxis.MajorUnit = 100.0d;
yAxis.MinorUnit = 20.0d;
yAxis.TickLabelPosition = AxisTickLabelPosition.NextToAxis;

// Gli istogrammi non hanno un asse Z.
Assert.Null(chart.AxisZ);

doc.Save(ArtifactsDir + "Charts.AxisProperties.docx");
```

### Guarda anche

* enum [AxisTickMark](../../axistickmark/)
* class [ChartAxis](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartaxis/)
* assemblea [Aspose.Words](../../../)


