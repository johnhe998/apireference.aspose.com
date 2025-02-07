---
title: Enum AxisBuiltInUnit
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.Charts.AxisBuiltInUnit Sıralama. Bir eksen için görüntüleme birimlerini belirtir.
type: docs
weight: 510
url: /tr/net/aspose.words.drawing.charts/axisbuiltinunit/
---
## AxisBuiltInUnit enumeration

Bir eksen için görüntüleme birimlerini belirtir.

```csharp
public enum AxisBuiltInUnit
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Grafikteki değerlerin olduğu gibi görüntüleneceğini belirtir. |
| Custom | `1` | Grafikteki değerlerin kullanıcı tanımlı bir bölenle bölüneceğini belirtir. Bu değer, MS Office 2016'nın yeni grafik türleri tarafından desteklenmez . |
| Billions | `2` | Grafikteki değerlerin 1.000.000.000'a bölüneceğini belirtir. |
| HundredMillions | `3` | Grafikteki değerlerin 100.000.000'a bölüneceğini belirtir. |
| Hundreds | `4` | Grafikteki değerlerin 100'e bölüneceğini belirtir. |
| HundredThousands | `5` | Grafikteki değerlerin 100.000'e bölüneceğini belirtir. |
| Millions | `6` | Grafikteki değerlerin 1.000.000'a bölüneceğini belirtir. |
| TenMillions | `7` | Grafikteki değerlerin 10.000.000'a bölüneceğini belirtir. |
| TenThousands | `8` | Grafikteki değerlerin 10.000'e bölüneceğini belirtir. |
| Thousands | `9` | Grafikteki değerlerin 1.000'e bölüneceğini belirtir. |
| Trillions | `10` | Grafikteki değerlerin 1.000.000.000.000.000'a bölüneceğini belirtir. |
| Percentage | `11` | Grafikteki değerlerin 0,01'e bölüneceğini belirtir. Bu değer yalnızca MS Office 2016'nın yeni chart türleri tarafından desteklenir. |

### Örnekler

Bir grafik ekseninin onay işaretlerinin ve görüntülenen değerlerinin nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);

// Y ekseninin küçük onay işaretlerini çizim alanından uzağa işaret edecek şekilde ayarlayın,
// ve ekseni geçmek için ana onay işaretleri.
ChartAxis axis = chart.AxisY;
axis.MajorTickMark = AxisTickMark.Cross;
axis.MinorTickMark = AxisTickMark.Outside;

// Y eksenini, her 10 birimde bir büyük bir onay işareti ve her 1 birimde bir küçük onay işareti gösterecek şekilde ayarlayın.
axis.MajorUnit = 10;
axis.MinorUnit = 1;

// Y ekseni sınırlarını -10 ve 20 olarak ayarlayın.
// Bu Y ekseni şimdi 4 ana onay işareti ve 27 küçük onay işareti gösterecektir.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(20);

// X ekseni için, ana onay işaretlerini her 10 birimde bir ayarlayın,
// 2.5 birimde her küçük onay işareti.
axis = chart.AxisX;
axis.MajorUnit = 10;
axis.MinorUnit = 2.5;

// Her iki onay işareti türünü de grafik çizim alanı içinde görünecek şekilde yapılandırın.
axis.MajorTickMark = AxisTickMark.Inside;
axis.MinorTickMark = AxisTickMark.Inside;

// X ekseni sınırlarını, X ekseni 5 ana çentik işaretine ve 12 küçük çentik işaretine yayılacak şekilde ayarlayın.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(30);
axis.TickLabelAlignment = ParagraphAlignment.Right;

Assert.AreEqual(1, axis.TickLabelSpacing);

// Değerlerini milyon olarak göstermek için onay etiketlerini ayarlayın.
axis.DisplayUnit.Unit = AxisBuiltInUnit.Millions;

// Onay etiketlerinin değerlerini göstereceği daha spesifik bir değer ayarlayabiliriz.
// Bu ifade yukarıdakine eşdeğerdir.
axis.DisplayUnit.CustomUnit = 1000000;
doc.Save(ArtifactsDir + "Charts.AxisDisplayUnit.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* toplantı [Aspose.Words](../../)


