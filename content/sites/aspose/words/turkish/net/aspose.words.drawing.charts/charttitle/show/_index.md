---
title: ChartTitle.Show
second_title: Aspose.Words for .NET API Referansı
description: ChartTitle mülk. Bu grafik için başlığın gösterilip gösterilmeyeceğini belirler. Varsayılan değer truedur.
type: docs
weight: 20
url: /tr/net/aspose.words.drawing.charts/charttitle/show/
---
## ChartTitle.Show property

Bu grafik için başlığın gösterilip gösterilmeyeceğini belirler. Varsayılan değer true'dur.

```csharp
public bool Show { get; set; }
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

* class [ChartTitle](../)
* ad alanı [Aspose.Words.Drawing.Charts](../../charttitle/)
* toplantı [Aspose.Words](../../../)


