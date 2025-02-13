---
title: Class ChartSeriesCollection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.Charts.ChartSeriesCollection sınıf. BirChartSeries .
type: docs
weight: 740
url: /tr/net/aspose.words.drawing.charts/chartseriescollection/
---
## ChartSeriesCollection class

Bir[`ChartSeries`](../chartseries/) .

```csharp
public class ChartSeriesCollection : IEnumerable<ChartSeries>
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words.drawing.charts/chartseriescollection/count/) { get; } | Sayısını döndürür[`ChartSeries`](../chartseries/) bu koleksiyonda. |
| [Item](../../aspose.words.drawing.charts/chartseriescollection/item/) { get; } | Bir döndürür[`ChartSeries`](../chartseries/) belirtilen dizinde. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_2)(string, DateTime[], double[]) | Yeni ekler[`ChartSeries`](../chartseries/) bu koleksiyona. Her tür Alan, Radar ve Hisse senedi grafiğine seri eklemek için bu yöntemi kullanın. |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add)(string, double[], double[]) | Yeni ekler[`ChartSeries`](../chartseries/) bu koleksiyona. Her tür Dağılım grafiğine seri eklemek için bu yöntemi kullanın. |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_3)(string, string[], double[]) | Yeni ekler[`ChartSeries`](../chartseries/)bu koleksiyona. Herhangi bir Çubuk, Sütun, Çizgi ve Yüzey grafiğine seri eklemek için bu yöntemi kullanın. |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_1)(string, double[], double[], double[]) | Yeni ekler[`ChartSeries`](../chartseries/) bu koleksiyona. Herhangi bir Bubble grafiği türüne seri eklemek için bu yöntemi kullanın. |
| [Clear](../../aspose.words.drawing.charts/chartseriescollection/clear/)() | Tümünü kaldırır[`ChartSeries`](../chartseries/) bu koleksiyondan. |
| [GetEnumerator](../../aspose.words.drawing.charts/chartseriescollection/getenumerator/)() | Bir numaralandırıcı nesnesi döndürür. |
| [RemoveAt](../../aspose.words.drawing.charts/chartseriescollection/removeat/)(int) | Bir[`ChartSeries`](../chartseries/) belirtilen dizinde. |

### Örnekler

Bir grafikte seri verilerinin nasıl ekleneceğini ve kaldırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Varsayılan olarak üç dizi demo verisi içerecek bir sütun grafiği ekleyin.
Shape chartShape = builder.InsertChart(ChartType.Column, 400, 300);
Chart chart = chartShape.Chart;

// Her serinin dört ondalık değeri vardır: dört kategorinin her biri için bir tane.
// Üç sütundan oluşan dört küme bu verileri temsil edecektir.
ChartSeriesCollection chartData = chart.Series;

Assert.AreEqual(3, chartData.Count);

// Grafikteki her serinin adını yazdırın.
using (IEnumerator<ChartSeries> enumerator = chart.Series.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Console.WriteLine(enumerator.Current.Name);
    }
}

// Bunlar grafikteki kategorilerin isimleridir.
string[] categories = { "Category 1", "Category 2", "Category 3", "Category 4" };

// Mevcut kategoriler için yeni değerler içeren bir dizi ekleyebiliriz.
// Bu grafik şimdi dört sütundan oluşan dört küme içerecek.
chart.Series.Add("Series 4", categories, new[] { 4.4, 7.0, 3.5, 2.1 });

// Bir grafik serisi, bunun gibi dizine göre de kaldırılabilir.
// Bu, grafikle birlikte gelen üç demo serisinden birini kaldıracaktır.
chartData.RemoveAt(2);

Assert.False(chartData.Any(s => s.Name == "Series 3"));

// Ayrıca bu yöntemle tüm grafiğin verilerini bir kerede temizleyebiliriz.
// Yeni bir grafik oluştururken, tüm demo verilerini silmenin yolu budur
// boş bir grafik üzerinde çalışmaya başlamadan önce.
chartData.Clear();
```

### Ayrıca bakınız

* class [ChartSeries](../chartseries/)
* ad alanı [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* toplantı [Aspose.Words](../../)


