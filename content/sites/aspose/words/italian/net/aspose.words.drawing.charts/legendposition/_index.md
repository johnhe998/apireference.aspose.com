---
title: Enum LegendPosition
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.Charts.LegendPosition enum. Specifica le possibili posizioni per una legenda del grafico.
type: docs
weight: 780
url: /it/net/aspose.words.drawing.charts/legendposition/
---
## LegendPosition enumeration

Specifica le possibili posizioni per una legenda del grafico.

```csharp
public enum LegendPosition
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Non verrà mostrata alcuna legenda per il grafico. |
| Bottom | `1` | Specifica che la legenda deve essere disegnata nella parte inferiore del grafico. |
| Left | `2` | Specifica che la legenda deve essere disegnata a sinistra del grafico. |
| Right | `3` | Specifica che la legenda deve essere disegnata a destra del grafico. |
| Top | `4` | Specifica che la legenda deve essere disegnata nella parte superiore del grafico. |
| TopRight | `5` | Specifica che la legenda deve essere disegnata in alto a destra nel grafico. |

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

* spazio dei nomi [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* assemblea [Aspose.Words](../../)


