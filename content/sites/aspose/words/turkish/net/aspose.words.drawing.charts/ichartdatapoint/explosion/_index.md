---
title: IChartDataPoint.Explosion
second_title: Aspose.Words for .NET API Referansı
description: IChartDataPoint mülk. Veri noktasının pastanın merkezinden taşınacağı miktarı belirtir. Negatif olabilir negatif olabilir özelliğin ayarlanmadığı ve patlama uygulanmaması gerektiği anlamına gelir. Yalnızca Pasta grafikler için geçerlidir.
type: docs
weight: 20
url: /tr/net/aspose.words.drawing.charts/ichartdatapoint/explosion/
---
## IChartDataPoint.Explosion property

Veri noktasının pastanın merkezinden taşınacağı miktarı belirtir. Negatif olabilir, negatif olabilir, özelliğin ayarlanmadığı ve patlama uygulanmaması gerektiği anlamına gelir. Yalnızca Pasta grafikler için geçerlidir.

```csharp
public int Explosion { get; set; }
```

### Örnekler

Pasta grafiğin dilimlerinin merkezden nasıl uzaklaştırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Pie, 500, 350);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Sales", chart.Series[0].Name);

// Bir pasta grafiğin "dilimleri", ilgili veri noktasının Patlama özniteliği aracılığıyla merkezden bir mesafe kadar uzağa taşınabilir.
// Pasta grafiğin ilk kısmına bir veri noktası ekleyin ve onu merkezden 10 puan uzaklaştırın.
// Aspose.Words veri noktaları yoksa otomatik olarak oluşturur.
ChartDataPoint dataPoint = chart.Series[0].DataPoints[0];
dataPoint.Explosion = 10;

// İkinci kısmı daha büyük bir mesafeye kaydır.
dataPoint = chart.Series[0].DataPoints[1];
dataPoint.Explosion = 40;

doc.Save(ArtifactsDir + "Charts.PieChartExplosion.docx");
```

### Ayrıca bakınız

* interface [IChartDataPoint](../)
* ad alanı [Aspose.Words.Drawing.Charts](../../ichartdatapoint/)
* toplantı [Aspose.Words](../../../)


