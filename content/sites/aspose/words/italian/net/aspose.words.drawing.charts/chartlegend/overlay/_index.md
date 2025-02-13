---
title: ChartLegend.Overlay
second_title: Aspose.Words per .NET API Reference
description: ChartLegend proprietà. Determina se altri elementi del grafico devono sovrapporsi alla legenda. Il valore predefinito è false.
type: docs
weight: 20
url: /it/net/aspose.words.drawing.charts/chartlegend/overlay/
---
## ChartLegend.Overlay property

Determina se altri elementi del grafico devono sovrapporsi alla legenda. Il valore predefinito è false.

```csharp
public bool Overlay { get; set; }
```

### Esempi

Mostra come modificare l'aspetto della legenda di un grafico.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 450, 300);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// Sposta la legenda del grafico nell'angolo in alto a destra.
ChartLegend legend = chart.Legend;
legend.Position = LegendPosition.TopRight;

// Concedi più spazio ad altri elementi del grafico, come il grafico, consentendo loro di sovrapporsi alla legenda.
legend.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartLegend.docx");
```

### Guarda anche

* class [ChartLegend](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartlegend/)
* assemblea [Aspose.Words](../../../)


