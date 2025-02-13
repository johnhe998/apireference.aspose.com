---
title: Interface IChartDataPoint
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.Charts.IChartDataPoint arayüz. Grafikteki tek bir veri noktasının özelliklerini içerir.
type: docs
weight: 770
url: /tr/net/aspose.words.drawing.charts/ichartdatapoint/
---
## IChartDataPoint interface

Grafikteki tek bir veri noktasının özelliklerini içerir.

```csharp
public interface IChartDataPoint
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Bubble3D](../../aspose.words.drawing.charts/ichartdatapoint/bubble3d/) { get; set; } | Kabarcık grafiğindeki baloncuklara 3-B efektinin uygulanıp uygulanmayacağını belirtir. |
| [Explosion](../../aspose.words.drawing.charts/ichartdatapoint/explosion/) { get; set; } | Veri noktasının pastanın merkezinden taşınacağı miktarı belirtir. Negatif olabilir, negatif olabilir, özelliğin ayarlanmadığı ve patlama uygulanmaması gerektiği anlamına gelir. Yalnızca Pasta grafikler için geçerlidir. |
| [InvertIfNegative](../../aspose.words.drawing.charts/ichartdatapoint/invertifnegative/) { get; set; } | Değer negatifse üst öğenin renklerini tersine çevirip çevirmeyeceğini belirtir. |
| [Marker](../../aspose.words.drawing.charts/ichartdatapoint/marker/) { get; } | Bir veri işaretçisini belirtir. İşaretleyici, istendiğinde otomatik olarak oluşturulur. |

### Örnekler

Çizgi grafikte veri noktalarıyla nasıl çalışılacağını gösterir.

```csharp
[Test]
public void ChartDataPoint()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    Shape shape = builder.InsertChart(ChartType.Line, 500, 350);
    Chart chart = shape.Chart;

    Assert.AreEqual(3, chart.Series.Count);
    Assert.AreEqual("Series 1", chart.Series[0].Name);
    Assert.AreEqual("Series 2", chart.Series[1].Name);
    Assert.AreEqual("Series 3", chart.Series[2].Name);

    // Grafiğin veri noktalarını elmas şekiller olarak göstererek vurgulayın.
    foreach (ChartSeries series in chart.Series) 
        ApplyDataPoints(series, 4, MarkerSymbol.Diamond, 15);

    // İlk veri serisini temsil eden satırı düzeltin.
    chart.Series[0].Smooth = true;

    // Değer negatifse, ilk seri için veri noktalarının renklerini tersine çevirmediğini doğrulayın.
    using (IEnumerator<ChartDataPoint> enumerator = chart.Series[0].DataPoints.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Assert.False(enumerator.Current.InvertIfNegative);
        }
    }

    // Daha temiz bir grafik için formatı tek tek temizleyebiliriz.
    chart.Series[1].DataPoints[2].ClearFormat();

    // Aynı anda bir dizi veri noktasının tamamını da ayıklayabiliriz.
    chart.Series[2].DataPoints.ClearFormat();

    doc.Save(ArtifactsDir + "Charts.ChartDataPoint.docx");
}

/// <summary>
/// Bir diziye bir dizi veri noktası uygular.
/// </summary>
private static void ApplyDataPoints(ChartSeries series, int dataPointsCount, MarkerSymbol markerSymbol, int dataPointSize)
{
    for (int i = 0; i < dataPointsCount; i++)
    {
        ChartDataPoint point = series.DataPoints[i];
        point.Marker.Symbol = markerSymbol;
        point.Marker.Size = dataPointSize;

        Assert.AreEqual(i, point.Index);
    }
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* toplantı [Aspose.Words](../../)


