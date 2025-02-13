---
title: Chart.Title
second_title: Aspose.Words for .NET API Referansı
description: Chart mülk. Grafik başlığı özelliklerine erişim sağlar.
type: docs
weight: 70
url: /tr/net/aspose.words.drawing.charts/chart/title/
---
## Chart.Title property

Grafik başlığı özelliklerine erişim sağlar.

```csharp
public ChartTitle Title { get; }
```

### Örnekler

Bir grafiğin nasıl ekleneceğini ve bir başlığın nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belge oluşturucu ile bir grafik şekli ekleyin ve grafiğini alın.
Shape chartShape = builder.InsertChart(ChartType.Bar, 400, 300);
Chart chart = chartShape.Chart;

// Grafiğimize, grafik alanının üst ortasında görünen bir başlık vermek için "Başlık" özelliğini kullanın.
ChartTitle title = chart.Title;
title.Text = "My Chart";

 // Başlığı görünür kılmak için "Show" özelliğini "true" olarak ayarlayın.
title.Show = true;

// "Kaplama" özelliğini "true" olarak ayarlayın Diğer grafik öğelerine, başlıkla çakışmalarına izin vererek daha fazla yer verin
title.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartTitle.docx");
```

### Ayrıca bakınız

* class [ChartTitle](../../charttitle/)
* class [Chart](../)
* ad alanı [Aspose.Words.Drawing.Charts](../../chart/)
* toplantı [Aspose.Words](../../../)


