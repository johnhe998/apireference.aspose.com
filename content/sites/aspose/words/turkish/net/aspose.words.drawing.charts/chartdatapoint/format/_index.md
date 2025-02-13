---
title: ChartDataPoint.Format
second_title: Aspose.Words for .NET API Referansı
description: ChartDataPoint mülk. Bu veri noktasının doldurma ve satır biçimlendirmesine erişim sağlar.
type: docs
weight: 30
url: /tr/net/aspose.words.drawing.charts/chartdatapoint/format/
---
## ChartDataPoint.Format property

Bu veri noktasının doldurma ve satır biçimlendirmesine erişim sağlar.

```csharp
public ChartFormat Format { get; }
```

### Örnekler

Sütun grafiğinin kategorileri için bireysel biçimlendirmenin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;

// Varsayılan oluşturulan serileri sil.
chart.Series.Clear();

// Yeni seriler ekleniyor.
ChartSeries series = chart.Series.Add("Series 1",
    new[] { "Category 1", "Category 2", "Category 3", "Category 4" },
    new double[] { 1, 2, 3, 4 });

// Sütun biçimlendirmesini ayarla.
ChartDataPointCollection dataPoints = series.DataPoints;
dataPoints[0].Format.Fill.PresetTextured(PresetTexture.Denim);
dataPoints[1].Format.Fill.ForeColor = Color.Red;
dataPoints[2].Format.Fill.ForeColor = Color.Yellow;
dataPoints[3].Format.Fill.ForeColor = Color.Blue;

doc.Save(ArtifactsDir + "Charts.DataPointsFormatting.docx");
```

### Ayrıca bakınız

* class [ChartFormat](../../chartformat/)
* class [ChartDataPoint](../)
* ad alanı [Aspose.Words.Drawing.Charts](../../chartdatapoint/)
* toplantı [Aspose.Words](../../../)


