---
title: IChartDataPoint.Explosion
second_title: Aspose.Words per .NET API Reference
description: IChartDataPoint proprietà. Specifica la quantità di spostamento del punto dati dal centro della torta. Può essere negativo negativo significa che la proprietà non è impostata e non deve essere applicata alcuna esplosione. Si applica solo ai grafici a torta.
type: docs
weight: 20
url: /it/net/aspose.words.drawing.charts/ichartdatapoint/explosion/
---
## IChartDataPoint.Explosion property

Specifica la quantità di spostamento del punto dati dal centro della torta. Può essere negativo, negativo significa che la proprietà non è impostata e non deve essere applicata alcuna esplosione. Si applica solo ai grafici a torta.

```csharp
public int Explosion { get; set; }
```

### Esempi

Mostra come spostare le sezioni di un grafico a torta lontano dal centro.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Pie, 500, 350);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Sales", chart.Series[0].Name);

// Le "fette" di un grafico a torta possono essere spostate dal centro di una distanza tramite l'attributo Esplosione del rispettivo punto dati.
// Aggiungi un punto dati alla prima parte del grafico a torta e allontanalo dal centro di 10 punti.
// Aspose.Words crea automaticamente punti dati se non esistono.
ChartDataPoint dataPoint = chart.Series[0].DataPoints[0];
dataPoint.Explosion = 10;

// Sposta la seconda porzione di una distanza maggiore.
dataPoint = chart.Series[0].DataPoints[1];
dataPoint.Explosion = 40;

doc.Save(ArtifactsDir + "Charts.PieChartExplosion.docx");
```

### Guarda anche

* interface [IChartDataPoint](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../ichartdatapoint/)
* assemblea [Aspose.Words](../../../)


