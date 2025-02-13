---
title: Enum LegendPosition
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.Charts.LegendPosition Sıralama. Bir grafik göstergesi için olası konumları belirtir.
type: docs
weight: 780
url: /tr/net/aspose.words.drawing.charts/legendposition/
---
## LegendPosition enumeration

Bir grafik göstergesi için olası konumları belirtir.

```csharp
public enum LegendPosition
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Grafik için gösterge gösterilmeyecek. |
| Bottom | `1` | Göstergenin grafiğin altına çizileceğini belirtir. |
| Left | `2` | Göstergenin grafiğin soluna çizileceğini belirtir. |
| Right | `3` | Göstergenin grafiğin sağ tarafında çizileceğini belirtir. |
| Top | `4` | Göstergenin grafiğin en üstüne çizileceğini belirtir. |
| TopRight | `5` | Göstergenin grafiğin sağ üst kısmına çizileceğini belirtir. |

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

* ad alanı [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* toplantı [Aspose.Words](../../)


