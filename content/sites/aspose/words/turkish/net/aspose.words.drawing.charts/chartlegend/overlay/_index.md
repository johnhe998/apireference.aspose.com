---
title: ChartLegend.Overlay
second_title: Aspose.Words for .NET API Referansı
description: ChartLegend mülk. Diğer grafik öğelerinin lejandla çakışmasına izin verilip verilmeyeceğini belirler. Varsayılan değer falsetur.
type: docs
weight: 20
url: /tr/net/aspose.words.drawing.charts/chartlegend/overlay/
---
## ChartLegend.Overlay property

Diğer grafik öğelerinin lejandla çakışmasına izin verilip verilmeyeceğini belirler. Varsayılan değer false'tur.

```csharp
public bool Overlay { get; set; }
```

### Örnekler

Bir grafiğin göstergesinin görünümünün nasıl düzenleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 450, 300);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// Grafiğin lejandını sağ üst köşeye taşıyın.
ChartLegend legend = chart.Legend;
legend.Position = LegendPosition.TopRight;

// Grafik gibi diğer grafik öğelerine lejandla örtüşmelerine izin vererek daha fazla alan verin.
legend.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartLegend.docx");
```

### Ayrıca bakınız

* class [ChartLegend](../)
* ad alanı [Aspose.Words.Drawing.Charts](../../chartlegend/)
* toplantı [Aspose.Words](../../../)


