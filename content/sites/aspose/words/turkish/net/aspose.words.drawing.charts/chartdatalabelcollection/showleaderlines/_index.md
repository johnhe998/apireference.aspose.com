---
title: ChartDataLabelCollection.ShowLeaderLines
second_title: Aspose.Words for .NET API Referansı
description: ChartDataLabelCollection mülk. Tüm serinin veri etiketleri için veri etiketi öncü çizgilerinin gösterilmesi gerekip gerekmediğini belirlemeye izin verir. Varsayılan değer yanlış .
type: docs
weight: 80
url: /tr/net/aspose.words.drawing.charts/chartdatalabelcollection/showleaderlines/
---
## ChartDataLabelCollection.ShowLeaderLines property

Tüm serinin veri etiketleri için veri etiketi öncü çizgilerinin gösterilmesi gerekip gerekmediğini belirlemeye izin verir. Varsayılan değer **yanlış** .

```csharp
public bool ShowLeaderLines { get; set; }
```

### Notlar

Yalnızca Pasta grafikler için geçerlidir. Öncü çizgiler, bir veri etiketi ile buna karşılık gelen veri noktası arasında görsel bir bağlantı oluşturur.

Bu özellik için tanımlanan değer, the kullanılarak tek bir veri etiketi için geçersiz kılınabilir[`ShowLeaderLines`](../../chartdatalabel/showleaderlines/) Emlak.

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


