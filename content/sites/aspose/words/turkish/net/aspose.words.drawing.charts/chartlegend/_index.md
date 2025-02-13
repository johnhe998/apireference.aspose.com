---
title: Class ChartLegend
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.Charts.ChartLegend sınıf. Grafik gösterge özelliklerini temsil eder.
type: docs
weight: 680
url: /tr/net/aspose.words.drawing.charts/chartlegend/
---
## ChartLegend class

Grafik gösterge özelliklerini temsil eder.

```csharp
public class ChartLegend
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [LegendEntries](../../aspose.words.drawing.charts/chartlegend/legendentries/) { get; } | Üst grafiğin tüm serileri ve eğilim çizgileri için gösterge girdilerinin bir koleksiyonunu döndürür. |
| [Overlay](../../aspose.words.drawing.charts/chartlegend/overlay/) { get; set; } | Diğer grafik öğelerinin lejandla çakışmasına izin verilip verilmeyeceğini belirler. Varsayılan değer false'tur. |
| [Position](../../aspose.words.drawing.charts/chartlegend/position/) { get; set; } | Göstergenin bir grafikteki konumunu belirtir. Varsayılan değerRight . |

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


