---
title: ChartDataLabelCollection.ShowPercentage
second_title: Aspose.Words for .NET API Referansı
description: ChartDataLabelCollection mülk. Tüm serinin veri etiketleri için yüzde değerinin gösterilip gösterilmeyeceğini belirlemeye izin verir. Varsayılan değer yanlış . Yalnızca Pasta grafikler için geçerlidir.
type: docs
weight: 100
url: /tr/net/aspose.words.drawing.charts/chartdatalabelcollection/showpercentage/
---
## ChartDataLabelCollection.ShowPercentage property

Tüm serinin veri etiketleri için yüzde değerinin gösterilip gösterilmeyeceğini belirlemeye izin verir. Varsayılan değer **yanlış** . Yalnızca Pasta grafikler için geçerlidir.

```csharp
public bool ShowPercentage { get; set; }
```

### Notlar

Bu özellik için tanımlanan değer, the kullanılarak tek bir veri etiketi için geçersiz kılınabilir[`ShowPercentage`](../../chartdatalabel/showpercentage/) özellik.

### Örnekler

Pasta grafiğin veri etiketleriyle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Pie, 500, 300).Chart;

// Temiz bir grafikle başlamak için grafiğin demo veri serisini temizleyin.
chart.Series.Clear();

// Sektörlerin her biri için bir kategori adı ve bunların sıklık tablosu ile özel bir grafik serisi ekleyin.
ChartSeries series = chart.Series.Add("Aspose Test Series",
    new[] { "Word", "PDF", "Excel" },
    new[] { 2.7, 3.2, 0.8 });

// Her sektörün hem yüzdesini hem de sıklığını gösterecek veri etiketlerini etkinleştirin ve görünümlerini değiştirin.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowLeaderLines = true;
dataLabels.ShowLegendKey = true;
dataLabels.ShowPercentage = true;
dataLabels.ShowValue = true;
dataLabels.Separator = "; ";

doc.Save(ArtifactsDir + "Charts.DataLabelsPieChart.docx");
```

### Ayrıca bakınız

* class [ChartDataLabelCollection](../)
* ad alanı [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* toplantı [Aspose.Words](../../../)


