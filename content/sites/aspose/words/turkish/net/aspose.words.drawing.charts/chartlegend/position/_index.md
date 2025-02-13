---
title: ChartLegend.Position
second_title: Aspose.Words for .NET API Referansı
description: ChartLegend mülk. Göstergenin bir grafikteki konumunu belirtir. Varsayılan değerRight .
type: docs
weight: 30
url: /tr/net/aspose.words.drawing.charts/chartlegend/position/
---
## ChartLegend.Position property

Göstergenin bir grafikteki konumunu belirtir. Varsayılan değerRight .

```csharp
public LegendPosition Position { get; set; }
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

* enum [LegendPosition](../../legendposition/)
* class [ChartLegend](../)
* ad alanı [Aspose.Words.Drawing.Charts](../../chartlegend/)
* toplantı [Aspose.Words](../../../)


